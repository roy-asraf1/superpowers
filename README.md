## מדריך עבודה עם Claude Code ו־Superpowers

המדריך מיועד למי שכבר התקין Superpowers.

אתה מתאר מה אתה רוצה, מאשר את התכנון ובודק את התוצאה.
קלוד מתכנן, מממש, מפעיל סוכנים ומבצע בדיקות.

### תהליך הפיתוח במבט אחד

| שלב | מה עושים | התוצאה |
|---|---|---|
| 1 | מכירים את הפרויקט | מבינים מה כבר קיים |
| 2 | מגדירים מה רוצים לבנות | הצעת אפיון |
| 3 | מאשרים אפיון כתוב | מסמך שמגדיר מה בונים |
| 4 | מכינים ומאשרים תוכנית | משימות ומבחני הצלחה |
| 5 | מממשים בסביבת עבודה מבודדת | קוד, בדיקות וביקורת |
| 6 | מאמתים ובודקים בעצמנו | תוצאה עובדת ומגבלות ברורות |
| 7 | מסיימים את השינוי | החלטה על PR, מיזוג או שמירת הענף |

התהליך המלא מתאים למערכת חדשה או לרכיב משמעותי.
לשינוי קטן בקוד קיים יש מסלול קצר בהמשך.

### שלב 1: פותחים את הפרויקט

פתח Claude Code בתיקיית הפרויקט שלך והתחל שיחה חדשה.

כתוב:

```text
בדוק ש־Superpowers זמין בשיחה הזאת.
קרא את README.md ואת ההנחיות של הפרויקט.
בדוק את הקוד הקיים וסכם מה כבר יש ומה חסר.
```

מה מקבלים: תמונה קצרה של מצב הפרויקט.

אם חסר `CLAUDE.md`, אפשר להכין נקודת התחלה באמצעות:

```text
/init
```

### שלב 2: מסבירים מה רוצים לבנות

בחר תוצאה אחת שאפשר להפעיל ולבדוק.

לדוגמה: לקוח בוחר תאריכים ומקבל תשובה אם הווילה פנויה.

כתוב:

```text
/superpowers:brainstorming
אני רוצה לבנות: [כתוב כאן מה אתה רוצה].
המטרה היא: [מה המשתמש יוכל לעשות בסוף].
בדוק את הקוד הקיים ושאל שאלה אחת בכל פעם אם חסר מידע.
הצע דרכי מימוש והמלץ על דרך פשוטה.
הגדר מה נכלל בשלב הזה ומה נדחה להמשך.
הצג לי את האפיון לבדיקה.
```

מה מקבלים: הסבר של מה בונים, איך זה יתנהג
ומה ייחשב להצלחה.

### שלב 3: מאשרים את האפיון הכתוב

אפיון = מה בונים ואיך המוצר צריך להתנהג.

קרא את ההצעה ובקש תיקונים אם צריך.
כשהיא מתאימה, כתוב:

```text
האפיון שהצגת מתאים לי.
שמור אותו במסמך לפי הנחיות Superpowers
והצג לי את הקובץ לקריאה.
```

במסלול המלא, ברירת המחדל היא:

```text
docs/superpowers/specs/YYYY-MM-DD-topic-design.md
```

קרא גם את הקובץ שנוצר.

אישור ההצעה בצ׳אט ואישור המסמך הכתוב
הם שני צעדים.

### שלב 4: מכינים ומאשרים תוכנית מימוש

תוכנית = איך בונים, צעד אחר צעד.

אחרי שקראת את מסמך האפיון והוא מתאים לך, כתוב:

```text
/superpowers:writing-plans
אני מאשר את מסמך האפיון.
כתוב תוכנית מימוש עם משימות ברורות.
ציין לכל משימה אילו קבצים משתנים
ואילו בדיקות יוכיחו שהמשימה הושלמה.
הצג לי את התוכנית לפני המימוש.
```

ברירת המחדל לשמירת התוכנית היא:

```text
docs/superpowers/plans/YYYY-MM-DD-feature.md
```

בדוק שהתוכנית מכסה את מה שביקשת
ושיש דרך לבדוק את התוצאה.

### שלב 5: מאשרים ביצוע ונותנים לקלוד לפתח

בחר אחת משתי דרכי הביצוע:

| דרך | איך עובדים |
|---|---|
| `subagent-driven-development` | סוכן מממש כל משימה וסוכן אחר בודק אותה; ביקורת כוללת בסוף |
| `executing-plans` | קלוד הנוכחי מממש את המשימות; ביקורת נפרדת בסוף |

לרכיב מורכב או חשוב, כתוב:

```text
/superpowers:subagent-driven-development
אני מאשר את התוכנית.
השתמש ב־using-git-worktrees להכנה של סביבת עבודה מבודדת.
בצע את התוכנית עם מימוש וביקורת לכל משימה.
המשך בין המשימות עד לסיום התוכנית.
בסיום בצע ביקורת כוללת והצג מה נבנה,
מה נבדק ומה עדיין חסר.
```

לתוכנית קצרה וברורה אפשר לבחור במסלול החסכוני יותר:

```text
/superpowers:executing-plans
אני מאשר את התוכנית.
עבוד בסביבת עבודה מבודדת.
בצע את המשימות עם בדיקות לאורך העבודה
וביקורת נפרדת בסיום.
```

סביבת עבודה מבודדת = תיקיית עבודה נפרדת
לאותו פרויקט, שבה מפתחים את השינוי.

#### מה קלוד עושה במהלך המימוש?

במסלול עם סוכנים, קלוד מנהל את המחזור הבא:

1. מכין הוראות למשימה.
2. סוכן המימוש כותב בדיקה ומריץ אותה לפני המימוש.
3. הסוכן מממש ומוודא שהבדיקה עוברת.
4. הסוכן שומר דוח על העבודה והבדיקות.
5. סוכן הביקורת בודק את השינוי.
6. מתקנים בעיות שנמצאו ומתעדים התקדמות.
7. ממשיכים למשימה הבאה.

TDD הוא המחזור:
בדיקה נכשלת, מימוש, בדיקה עוברת ושיפור הקוד.

המשימות במסלול הזה מתבצעות ברצף,
עם ביקורת ביניהן.

### שלב 6: בודקים שהתוצאה באמת עובדת

בסיום כתוב:

```text
/superpowers:verification-before-completion
הרץ את הבדיקות ואת בדיקת הבנייה המתאימות לפרויקט.
הצג מה עבר, מה נכשל ומה לא נבדק.
בדוק שהתוצאה תואמת לאפיון.
הסבר לי איך להפעיל את הפרויקט
ואיך לבדוק בעצמי את התרחיש שבנינו.
```

פתח את המוצר ובצע את הפעולה שביקשת לבנות.

לדוגמה, במנגנון זמינות:

- בדוק תאריכים פנויים.
- בדוק תאריכים תפוסים.
- בדוק מה קורה כשחסר מידע.

השלב הושלם כשהפעולה עובדת,
הבדיקות המתאימות עברו והמגבלות שנותרו ברורות.

אם חסרה ביקורת קוד, אפשר לבקש אותה באמצעות:

```text
/superpowers:requesting-code-review
```

### שלב 7: מסיימים את השינוי

כתוב:

```text
/superpowers:finishing-a-development-branch
סכם מה השתנה, מה נבדק ומה עדיין חסר.
הצג את אפשרויות הסיום של הענף.
```

ענף הוא גרסת העבודה של השינוי.

PR הוא בקשה לסקור ולהכניס את השינוי
לענף הראשי.

בחר את האפשרות שמתאימה לך לאחר הסקירה.
מיזוג קוד ופרסום המוצר הם פעולות נפרדות.

### כשיש תקלה

שלח לקלוד:

1. מה עשית.
2. מה ציפית שיקרה.
3. מה קרה בפועל.

הוסף הודעת שגיאה או צילום מסך אם יש.

כתוב:

```text
/superpowers:systematic-debugging
התקלה היא: [תאר כאן].
שחזר אותה, מצא את הסיבה,
הוסף בדיקה שמזהה את התקלה,
תקן והריץ את הבדיקות המתאימות.
```

### כשחוזרים אחרי הפסקה

כתוב:

```text
קרא את האפיון, את התוכנית ואת רישום ההתקדמות אם קיים.
בדוק את השינויים ואת ה־commits שכבר נעשו.
סכם מה הושלם ומה המשימה הבאה.
המשך מהנקודה שבה עצרנו.
```

### כשמדובר בשינוי קטן בקוד קיים

למשל: הוספת שדה לטופס קיים.

כתוב:

```text
/superpowers:brainstorming
השתמש במסלול Bounded.
אני רוצה: [תאר את השינוי].
בדוק את הקוד והצג הצעת שינוי קצרה בצ׳אט,
כולל איך תבדוק אותה.
```

אחרי שההצעה מתאימה:

```text
אני מאשר את ההצעה.
בצע את השינוי ואת הבדיקות המתאימות והצג את התוצאה.
```

במסלול הזה מספיק תכנון קצר בצ׳אט.
אם מתגלה שינוי ארכיטקטוני, עוברים לתהליך המלא.

### איזה קובץ עושה מה?

קובץ `.md` הוא טקסט בפורמט Markdown.
קובץ `.json` מכיל הגדרות במבנה מסודר.

| קובץ | תפקיד |
|---|---|
| `README.md` | הסבר על הפרויקט, ההפעלה ותהליך העבודה |
| `CLAUDE.md` | הנחיות קבועות לקלוד: כללים, מבנה הפרויקט ופקודות בדיקה |
| `CLAUDE.local.md` | הנחיות אישיות שלך לפרויקט |
| `.claude/rules/testing.md` | כללים בנושא מסוים; בדוגמה הזאת, בדיקות |
| `.claude/agents/code-reviewer.md` | הגדרת סוכן: שם, תפקיד וכלים |
| `.claude/skills/review/SKILL.md` | הגדרת Skill שאפשר להפעיל באמצעות `/review` |
| `.claude/commands/review.md` | דרך ותיקה, שעדיין נתמכת, להגדרת פקודה אישית |
| `.claude/settings.json` | הגדרות הפרויקט, כגון הרשאות, תוספים ו־Hooks |
| `.claude/settings.local.json` | הגדרות אישיות שלך לפרויקט |

`.claude/` נמצאת בתוך הפרויקט.

`~/.claude/` היא התיקייה האישית שלך במחשב.

השם המקובל הוא `CLAUDE.md` באותיות גדולות.

דוגמה לתוכן שלו:

```markdown
# הנחיות לפרויקט

- קרא את README.md כדי להבין את הפרויקט.
- השתמש בתהליך Superpowers המתאים לגודל המשימה.
- שמור אפיונים ב־docs/superpowers/specs/.
- שמור תוכניות מימוש ב־docs/superpowers/plans/.
- השתמש בפקודות ההפעלה והבדיקה הקיימות בפרויקט.
```

ייתכן שתראה גם `AGENTS.md`,
שמכיל הנחיות לכלי קוד.

הטעינה הישירה שלו בקלוד נתמכת מגרסה 2.1.277.
כשקיים `CLAUDE.md` של הפרויקט,
ברירת המחדל היא לטעון אותו במקום `AGENTS.md`.

### סוכן לעומת Skill

| מושג | הסבר פשוט |
|---|---|
| Agent — סוכן | מבצע משימה בחלון הקשר משלו |
| Skill — מיומנות | מגדיר תהליך עבודה |
| פקודת `/` | מפעילה פקודה או Skill |
| קובץ הגדרת סוכן | ההוראות שהסוכן קורא |
| דוח סוכן | התוצאה שהסוכן מחזיר בשיחה או כותב לקובץ שנקבע |

`brainstorming` ו־`writing-plans` הם Skills.

קובץ שמגדיר סוכן ויעד הדוח שלו
הם שני דברים נפרדים.

### מי הם הסוכנים ולאן הם כותבים?

| שם או תפקיד | מה עושה | תוצר |
|---|---|---|
| קלוד הראשי / Controller | מתכנן, מחלק משימות ומתעד התקדמות | אפיון, תוכנית ו־`progress.md` לפי השלב |
| `Explore` | סוכן מובנה לחיפוש וחקירה | מחזיר מידע לשיחה |
| `Plan` | סוכן מובנה לחקירה ותכנון | מחזיר הצעות לשיחה |
| `general-purpose` | סוכן מובנה למשימות כלליות | תוצר לפי המשימה והכלים |
| Implementer | תפקיד המממש ב־Superpowers | קוד, בדיקות ו־`task-N-report.md` |
| Task reviewer | תפקיד בודק המשימה ב־Superpowers | מחזיר ממצאים בשיחה |
| Final reviewer | תפקיד הבודק הסופי ב־Superpowers | מחזיר ממצאים בשיחה |

תפקידי Superpowers נוצרים במהלך הריצה.
הם אינם בהכרח סוכנים קבועים
ברשימת הסוכנים שלך.

### איפה נשמרים קובצי העבודה של הסוכנים?

בתהליך שנבדק בריפו,
קובצי העבודה נמצאים ב־:

```text
.superpowers/sdd/<plan-name>/
```

| קובץ | מי מייצר | מה יש בתוכו |
|---|---|---|
| `progress.md` | קלוד הראשי | התקדמות והחלטות |
| `task-N-brief.md` | כלי התהליך בהפעלת קלוד הראשי | הוראות למשימה |
| `task-N-report.md` | סוכן המימוש | מה בוצע ומה נבדק |
| `review-<base>..<head>.diff` | כלי התהליך בהפעלת קלוד הראשי | שינויי הקוד לביקורת |

`N` הוא מספר המשימה.

לדוגמה:
`task-3-report.md` הוא דוח המימוש של משימה 3.

קובצי העבודה האלה זמניים
ויכולים להימחק בסיום.

קלוד גם מנהל זיכרון אוטומטי,
בדרך כלל ב־:

```text
~/.claude/projects/<project>/memory/
```

`MEMORY.md` מפנה לזיכרונות לפי נושא.

הזיכרון האוטומטי ורישום ההתקדמות
של תוכנית הם מנגנונים נפרדים.

### איך מפעילים פקודות וסוכנים?

#### Skills של Superpowers

כתוב `/superpowers:`
ובחר מההשלמה האוטומטית.

השמות במדריך תואמים למבנה ה־Skills
בגרסה שנבדקה.

בחר את השם שמופיע אצלך,
כי גרסאות שונות עשויות לחשוף פקודות שונות.

#### סוכן מוגדר

בגרסאות שתומכות באזכור סוכנים,
אם מוגדר אצלך סוכן בשם `code-reviewer`,
אפשר לכתוב:

```text
@agent-code-reviewer בדוק את מנגנון ההזמנות
```

שם הסוכן נקבע בשדה `name:`
בקובץ ההגדרה.

מהטרמינל אפשר להתחיל שיחה שלמה
בתפקיד שלו:

```bash
claude --agent code-reviewer
```

#### פקודות עזר

| פקודה | שימוש |
|---|---|
| `/init` | הכנת נקודת התחלה ל־CLAUDE.md |
| `/memory` | צפייה ועריכה של הנחיות וזיכרון |
| `/agents` | עזרה בניהול הגדרות סוכנים |

בגרסאות ישנות `/agents` פותחת מסך ניהול.
בחדשות היא מציגה הנחיות לעריכת ההגדרות.

### איך יוצרים /review משלך?

זאת דוגמה אישית,
שאפשר להוסיף לפי צורך.

ראשית מגדירים סוכן בקובץ:

```text
.claude/agents/code-reviewer.md
```

תוכן הקובץ:

```markdown
---
name: code-reviewer
description: Review code for correctness and missing tests
tools: Read, Grep, Glob
---

בדוק את הקבצים שקיבלת.
החזר ממצאים עם שם הקובץ, מיקום הבעיה והצעת תיקון.
פעל בקריאה בלבד והחזר את הדוח בשיחה.
```

לאחר מכן יוצרים:

```text
.claude/skills/review/SKILL.md
```

תוכן הקובץ:

```markdown
---
name: review
description: Run the project's code reviewer
context: fork
agent: code-reviewer
disable-model-invocation: true
---

בדוק את הקבצים הבאים: $ARGUMENTS
החזר ממצאים לגבי תקינות הקוד ובדיקות חסרות.
```

כעת אפשר להריץ:

```text
/review src/booking.ts
```

החלף את הנתיב בקובץ אמיתי בפרויקט.

- `name: review` קובע את שם הפקודה.
- `context: fork` יוצר הקשר נפרד למשימה.
- `agent: code-reviewer` בוחר את הסוכן.
- `disable-model-invocation: true` קובע הפעלה ידנית.
- `$ARGUMENTS` הוא הטקסט שכתבת אחרי הפקודה.

בדוגמה הזאת הדוח חוזר בשיחה.

לדוח בקובץ צריך להגדיר גם יעד
וגם כלי כתיבה מתאימים.

### מקורות

- [Superpowers](https://github.com/roy-asraf1/superpowers)
- [קבצי הנחיות וזיכרון](https://code.claude.com/docs/en/memory)
- [Skills ופקודות](https://code.claude.com/docs/en/skills)
- [סוכנים והפעלתם](https://code.claude.com/docs/en/sub-agents)
- [קבצי הגדרות](https://code.claude.com/docs/en/settings)


# Superpowers

Superpowers is a complete software development methodology for your coding agents, built on top of a set of composable skills and some initial instructions that make sure your agent uses them.

## Table of Contents

- [How it works](#how-it-works)
- [Commercial Services](#commercial-services)
- [Getting Started](#installation)
  - [Claude Code](#claude-code)
  - [Antigravity](#antigravity)
  - [Codex App](#codex-app)
  - [Codex CLI](#codex-cli)
  - [Cursor](#cursor)
  - [Devin CLI](#devin-cli)
  - [Factory Droid](#factory-droid)
  - [Gemini CLI](#gemini-cli)
  - [GitHub Copilot CLI](#github-copilot-cli)
  - [Grok Build CLI](#grok-build-cli)
  - [Kimi Code](#kimi-code)
  - [OpenCode](#opencode)
  - [Pi](#pi)
  - [Qwen Code](#qwen-code)
  - [Hermes Agent](#hermes-agent)
  - [Muse](#muse)
- [The Basic Workflow](#the-basic-workflow)
- [When Something Goes Wrong](#when-something-goes-wrong)
- [Community](#community)
- [What's Inside](#whats-inside)
- [Philosophy](#philosophy)
- [Contributing](#contributing)
- [Updating](#updating)
- [License](#license)
- [Visual companion telemetry](#visual-companion-telemetry)

## How it works

It starts from the moment you fire up your coding agent. As soon as it sees that you're building something, it *doesn't* just jump into trying to write code. Instead, it steps back and asks you what you're really trying to do. 

Once it's teased a spec out of the conversation, it shows it to you in chunks short enough to actually read and digest. 

After you've signed off on the design, your agent puts together an implementation plan that's clear enough for an enthusiastic junior engineer with poor taste, no judgement, no project context, and an aversion to testing to follow. It emphasizes true red/green TDD, YAGNI (You Aren't Gonna Need It), and DRY. 

Next up, once you say "go", it launches a *subagent-driven-development* process, having agents work through each engineering task, inspecting and reviewing their work, and continuing forward. It's not uncommon for your agent to work autonomously for a couple hours at a time without deviating from the plan you put together.

There's a bunch more to it, but that's the core of the system. And because the skills trigger automatically, you don't need to do anything special. Your coding agent just has Superpowers.

## Commercial Services

If you're using Superpowers in enterprise and could benefit from commercial support, additional tooling, or managed spending, please don't hesitate to drop us a line at sales@primeradiant.com.

## Installation

Installation differs by harness. If you use more than one, install Superpowers separately for each one.

### Claude Code

Superpowers is available via the [official Claude plugin marketplace](https://claude.com/plugins/superpowers)

#### Official Marketplace

- Install the plugin from Anthropic's official marketplace:

  ```bash
  /plugin install superpowers@claude-plugins-official
  ```

#### Superpowers Marketplace

The Superpowers marketplace provides Superpowers and some other related plugins for Claude Code.

- Register the marketplace:

  ```bash
  /plugin marketplace add obra/superpowers-marketplace
  ```

- Install the plugin from this marketplace:

  ```bash
  /plugin install superpowers@superpowers-marketplace
  ```

### Antigravity

Install Superpowers as a plugin from this repository:

```bash
agy plugin install https://github.com/obra/superpowers
```

Antigravity runs the plugin's session-start hook, so Superpowers is active from
the first message. Reinstall with the same command to update.

### Codex App

Superpowers is available via the [official Codex plugin marketplace](https://github.com/openai/plugins).

- In the Codex app, click on Plugins in the sidebar.
- You should see `Superpowers` in the Coding section.
- Click the `+` next to Superpowers and follow the prompts.

### Codex CLI

Superpowers is available via the [official Codex plugin marketplace](https://github.com/openai/plugins).

- Open the plugin search interface:

  ```bash
  /plugins
  ```

- Search for Superpowers:

  ```bash
  superpowers
  ```

- Select `Install Plugin`.

### Cursor

- In Cursor Agent chat, install from marketplace:

  ```text
  /add-plugin superpowers
  ```

- Or search for "superpowers" in the plugin marketplace.

### Devin CLI

- Install the plugin from this repository:

  ```bash
  devin plugins install obra/superpowers
  ```

- Update to the latest version with:

  ```bash
  devin plugins update superpowers
  ```

### Factory Droid

- Register the marketplace:

  ```bash
  droid plugin marketplace add https://github.com/obra/superpowers
  ```

- Install the plugin:

  ```bash
  droid plugin install superpowers@superpowers
  ```

### Gemini CLI

- Install the extension:

  ```bash
  gemini extensions install https://github.com/obra/superpowers
  ```

- Update later:

  ```bash
  gemini extensions update superpowers
  ```

### GitHub Copilot CLI

- Register the marketplace:

  ```bash
  copilot plugin marketplace add obra/superpowers-marketplace
  ```

- Install the plugin:

  ```bash
  copilot plugin install superpowers@superpowers-marketplace
  ```

### Grok Build CLI

Superpowers is available via the [official Grok plugin marketplace](https://github.com/xai-org/plugin-marketplace).

- Install the plugin from xAI's official marketplace:

  ```bash
  grok plugin install superpowers@xai-official --trust
  ```

- Or open the marketplace in the TUI, search for Superpowers, and install it:

  ```text
  /marketplace
  ```

### Kimi Code

Superpowers is available in Kimi Code's plugin marketplace.

- Open Kimi Code's plugin manager:

  ```text
  /plugins
  ```

- Go to `Marketplace` > `Superpowers` and install it.

- Or install directly from this repository:

  ```text
  /plugins install https://github.com/obra/superpowers
  ```

- Detailed docs: [docs/README.kimi.md](docs/README.kimi.md)

### OpenCode

OpenCode uses its own plugin install; install Superpowers separately even if you
already use it in another harness.

- Tell OpenCode:

  ```
  Fetch and follow instructions from https://raw.githubusercontent.com/obra/superpowers/refs/heads/main/.opencode/INSTALL.md
  ```

- Detailed docs: [docs/README.opencode.md](docs/README.opencode.md)

### Pi

Install Superpowers as a Pi package from this repository:

```bash
pi install git:github.com/obra/superpowers
```

For local development, run Pi with this checkout loaded as a temporary package:

```bash
pi -e /path/to/superpowers
```

The Pi package loads the Superpowers skills and a small extension that injects the `using-superpowers` bootstrap at session startup and again after compaction. Pi has native skills, so no compatibility `Skill` tool is required. Subagent and task-list tools remain optional Pi companion packages.

### Qwen Code

Qwen Code installs plugins from Claude Code marketplaces directly.

- Install the plugin from this repository, and pick `superpowers` when prompted:

  ```bash
  qwen extensions install obra/superpowers
  ```

- Update later:

  ```bash
  qwen extensions update superpowers
  ```

### Hermes Agent

Install Superpowers as a Hermes plugin from this repository:

```bash
hermes plugins install obra/superpowers --enable
```

Restart any active Hermes sessions after installing. Note: Hermes has no
post-compaction hook, so a very long session that compacts over its first
turn loses the bootstrap — start a fresh session if skills stop triggering.

### Muse

Superpowers is available as a native Muse plugin — same repo, same skills, all harnesses. The `using-superpowers` bootstrap is injected via the native `SessionStart` hook alongside Claude Code, Codex, Cursor, Gemini, Pi, and the rest — no per-session opt-in.

- Install from a local checkout:

  ```bash
  muse plugins install ./
  muse plugins approve superpowers
  ```

  Or clone and install:

  ```bash
  git clone https://github.com/obra/superpowers.git
  muse plugins install ./superpowers
  muse plugins approve superpowers
  ```

- Update later:

  ```bash
  muse plugins update superpowers
  ```

Restart any active Muse sessions after installing so the `SessionStart` hook takes effect — skills are active immediately, hooks require approval on first install. To verify, start a fresh session and send `Let's make a react todo list` — a working install auto-triggers `brainstorming` before any code is written. Version is tracked in `.version-bump.json` so `scripts/bump-version.sh` keeps it in sync.

## The Basic Workflow

1. **brainstorming** - Activates before writing code. Refines rough ideas through questions, explores alternatives, presents design in sections for validation. Saves design document.

2. **using-git-worktrees** - Activates after design approval. Creates isolated workspace on new branch, runs project setup, verifies clean test baseline.

3. **writing-plans** - Activates with approved design. Breaks work into bite-sized tasks (2-5 minutes each). Every task has exact file paths, complete code, verification steps.

4. **subagent-driven-development** or **executing-plans** - Activates with plan. Either dispatches a fresh subagent per task with a review after each (most thorough), or implements every task inline in the current session with one fresh review of the whole branch at the end (cheapest).

5. **test-driven-development** - Activates during implementation. Enforces RED-GREEN-REFACTOR: write failing test, watch it fail, write minimal code, watch it pass, commit. Deletes code written before tests.

6. **requesting-code-review** - Activates between tasks. Reviews against plan, reports issues by severity. Critical issues block progress.

7. **finishing-a-development-branch** - Activates when tasks complete. Verifies tests, presents options (merge/PR/keep/discard), cleans up worktree.

**The agent checks for relevant skills before any task.** Mandatory workflows, not suggestions.

## When Something Goes Wrong

Sometimes a session misbehaves: a skill fires when it shouldn't, stays silent when it should, or the agent ignores its plan, repeats work, or burns more tokens than you'd expect. Ask your coding agent to "figure out what went wrong with superpowers in this session" and it will invoke the **diagnosing-superpowers** skill. To examine an earlier session, name it: "figure out what went wrong with superpowers in session `<id>`".

The skill reads the session transcript, reports what happened with line-level evidence, and, if you want, packages a scrubbed bundle for a bug report.

## Community

Superpowers is built by [Jesse Vincent](https://blog.fsck.com) and the rest of the folks at [Prime Radiant](https://primeradiant.com).

- **Discord**: [Join us](https://discord.gg/35wsABTejz) for community support, questions, and sharing what you're building with Superpowers
- **Issues**: https://github.com/obra/superpowers/issues
- **Release announcements**: [Sign up](https://primeradiant.com/superpowers/) to get notified about new versions

## What's Inside

### Skills Library

**Testing**
- **test-driven-development** - RED-GREEN-REFACTOR cycle (includes testing anti-patterns reference)

**Debugging**
- **systematic-debugging** - 4-phase root cause process (includes root-cause-tracing, defense-in-depth, condition-based-waiting techniques)
- **verification-before-completion** - Ensure it's actually fixed
- **diagnosing-superpowers** - Work out what went wrong in a session, with evidence; export a scrubbed bundle or file an issue

**Collaboration** 
- **brainstorming** - Socratic design refinement
- **writing-plans** - Detailed implementation plans
- **executing-plans** - Inline plan execution: one context, one final review
- **dispatching-parallel-agents** - Concurrent subagent workflows
- **requesting-code-review** - Pre-review checklist
- **receiving-code-review** - Responding to feedback
- **using-git-worktrees** - Parallel development branches
- **finishing-a-development-branch** - Merge/PR decision workflow
- **subagent-driven-development** - Fast iteration with two-stage review (spec compliance, then code quality)

**Meta**
- **writing-skills** - Create new skills following best practices (includes testing methodology)
- **using-superpowers** - Introduction to the skills system

## Philosophy

- **Test-Driven Development** - Write tests first, always
- **Systematic over ad-hoc** - Process over guessing
- **Complexity reduction** - Simplicity as primary goal
- **Evidence over claims** - Verify before declaring success

Read [the original release announcement](https://blog.fsck.com/2025/10/09/superpowers/).

## Contributing

The general contribution process for Superpowers is below. Keep in mind that we don't generally accept contributions of new skills and that any updates to skills must work across all of the coding agents we support.

1. Fork the repository
2. Switch to the 'dev' branch
3. Create a branch for your work
4. Follow the `writing-skills` skill for creating and testing new and modified skills
5. Submit a PR, being sure to fill in the pull request template.

Skill-behavior tests use the drill eval harness from [superpowers-evals](https://github.com/prime-radiant-inc/superpowers-evals/), cloned into `evals/` — see `evals/README.md` for setup. Plugin-infrastructure tests live at `tests/` and run via the relevant `run-*.sh` or `npm test`.

See `skills/writing-skills/SKILL.md` for the complete guide.

## Updating

Superpowers updates are somewhat coding-agent dependent, but are often automatic.

## License

MIT License - see LICENSE file for details

## Visual companion telemetry

Because skills and plugins don't provide any feedback to creators, we have no idea how many of you are using Superpowers. By default, the Prime Radiant logo on brainstorming's optional visual companion feature is loaded from our website. It includes the version of Superpowers in use. It does not include any details about your project, prompt, or coding agent. We don't see your clicks or anything about what you're building. This helps us have a rough idea of how many folks are using Superpowers and which version of Superpowers they're using. It's 100% optional. To disable this, set the environment variable `SUPERPOWERS_DISABLE_TELEMETRY` to any true value. Superpowers also honors Claude Code's `DISABLE_TELEMETRY` and `CLAUDE_CODE_DISABLE_NONESSENTIAL_TRAFFIC` opt-outs.
