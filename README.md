

## איך עובדים עם Superpowers ב־Claude Code

המדריך מיועד למי שכבר התקין Superpowers.

אתה מסביר מה אתה רוצה ובודק את התוצאה.
קלוד מתכנן, כותב את הקוד ומבצע בדיקות.
אפשר לכתוב לו בעברית.

### 1. פותחים את הפרויקט

פתח Claude Code בתיקיית הפרויקט שאתה רוצה לפתח.
התחל שיחה חדשה וכתוב:

> בדוק ש־Superpowers זמין בשיחה הזאת. קרא את ה־README
> ואת ההנחיות של הפרויקט, בדוק את הקוד הקיים וסכם בקצרה
> מה כבר יש ומה חסר.

מה מקבלים: הסבר קצר על מצב הפרויקט.

אם Superpowers אינו זמין, מסדרים את ההתקנה לפני שממשיכים.

### 2. מסבירים מה רוצים לבנות

בחר בכל פעם תוצאה אחת שאפשר להפעיל ולבדוק.

לדוגמה:
"אני רוצה שלקוח יבחר תאריכים ויקבל תשובה אם הווילה פנויה".

כתוב לקלוד:

> השתמש ב־brainstorming.
> אני רוצה: [כתוב כאן מה אתה רוצה לבנות].
> המטרה היא: [מה המשתמש יוכל לעשות בסוף].
> בדוק את הקוד הקיים ושאל שאלה אחת בכל פעם אם חסר מידע.
> הצע דרך פשוטה לביצוע והגדר מה נכלל בשלב הזה
> ומה נשאר להמשך.

מה מקבלים: הצעה ברורה של מה בונים ואיך זה יעבוד.

### 3. בודקים ומאשרים את האפיון

אפיון = מה בונים ואיך זה צריך להתנהג.

קרא את ההצעה של קלוד.
אם משהו חסר או שגוי, בקש לתקן אותו.

כשההצעה מתאימה, כתוב:

> האפיון שהצגת מתאים לי. שמור אותו במסמך לפי הנחיות
> Superpowers והצג לי את הקובץ לקריאה.

קרא את המסמך. אחרי שהוא מתאים לך, כתוב:

> אני מאשר את מסמך האפיון.
> השתמש ב־writing-plans וכתוב תוכנית מימוש
> עם משימות ברורות ובדיקות לכל משימה.

מה מקבלים: תוכנית עבודה שמבוססת על האפיון שאישרת.

### 4. מאשרים את התוכנית ומתחילים לפתח

תוכנית = איך בונים, צעד אחר צעד.

בדוק שהתוכנית כוללת את מה שביקשת
ושיש דרך לבדוק את התוצאה של כל משימה.

לרכיב מורכב או חשוב, כתוב:

> אני מאשר את התוכנית.
> השתמש ב־subagent-driven-development וב־using-git-worktrees.
> עבוד בסביבת עבודה מבודדת.
> השתמש בסוכן שמממש כל משימה ובסוכן אחר שבודק אותה.
> בצע את הבדיקות הנדרשות והמשך עד לסיום התוכנית.
> בסוף הצג מה נבנה, מה נבדק ומה עדיין חסר.

סביבת עבודה מבודדת = תיקיית עבודה נפרדת לאותו פרויקט,
שבה מפתחים את השינוי.

במסלול הזה העבודה מתבצעת כך:

1. סוכן מממש משימה.
2. סוכן אחר בודק את השינוי.
3. מתקנים בעיות שנמצאו.
4. ממשיכים למשימה הבאה.

לתוכנית קצרה וברורה אפשר לבחור מסלול חסכוני יותר:

> אני מאשר את התוכנית.
> השתמש ב־executing-plans בסביבת עבודה מבודדת.
> בצע את המשימות בעצמך, עם בדיקות לאורך העבודה
> וביקורת נפרדת בסיום.

בחר אחת משתי ההודעות.

### 5. בודקים שהתוצאה באמת עובדת

בסיום העבודה כתוב:

> השתמש ב־verification-before-completion.
> הרץ את הבדיקות ואת בדיקת הבנייה המתאימות לפרויקט.
> הצג אילו בדיקות עברו, אילו נכשלו ומה לא נבדק.
> הסבר לי בפשטות איך להפעיל את הפרויקט
> ואיך לבדוק בעצמי את התרחיש שבנינו.

פתח את המוצר ובצע את הפעולה שביקשת לבנות.

לדוגמה, בבדיקת זמינות של וילה:

- בחר תאריכים פנויים ובדוק שהתשובה נכונה.
- בחר תאריכים תפוסים ובדוק שהתשובה נכונה.
- בדוק מה קורה כשחסר מידע.

השלב הושלם כאשר:

- הפעולה שביקשת עובדת.
- הבדיקות המתאימות עברו.
- ברור מה עדיין חסר או לא נבדק.

אחרי הסקירה מחליטים על מיזוג השינוי ועל פרסום.

### 6. כשיש תקלה

שלח לקלוד שלושה דברים:

1. מה עשית.
2. מה ציפית שיקרה.
3. מה קרה בפועל.

הוסף הודעת שגיאה או צילום מסך אם יש.

כתוב:

> השתמש ב־systematic-debugging.
> התקלה היא: [תאר כאן את התקלה].
> שחזר אותה, מצא את הסיבה,
> הוסף בדיקה שמזהה את התקלה,
> תקן והריץ את הבדיקות המתאימות.

### 7. כשחוזרים לעבוד אחרי הפסקה

פתח את הפרויקט וכתוב:

> קרא את האפיון, את התוכנית ואת רישום ההתקדמות אם קיים.
> בדוק את השינויים ואת ה־commits שכבר נעשו.
> סכם מה הושלם ומה המשימה הבאה,
> והמשך מהנקודה שבה עצרנו.

מה מקבלים: המשך עבודה שמבוסס על מצב הפרויקט בפועל.

### 8. כשמדובר בשינוי קטן

למשל: הוספת שדה לטופס שכבר קיים.

אפשר להשתמש במסלול הקצר:

> השתמש ב־brainstorming במסלול Bounded.
> אני רוצה: [תאר כאן את השינוי].
> בדוק את הקוד והצג לי הצעת שינוי קצרה בצ׳אט,
> כולל איך תבדוק אותה.

כשההצעה מתאימה, כתוב:

> אני מאשר את ההצעה.
> בצע את השינוי ואת הבדיקות המתאימות
> והצג לי את התוצאה.

במסלול הזה מספיק תכנון קצר בצ׳אט.
אם מתגלה שינוי ארכיטקטוני, עוברים לתהליך המלא.

### ארבעה דברים שכדאי לזכור

- בחר בכל פעם תוצאה אחת שאפשר להפעיל ולבדוק.
- תקן אי־הבנות באפיון לפני המימוש.
- קרא את סיכום הבדיקות ובדוק גם בעצמך את הפעולה המרכזית.
- שמור את האפיון ואת התוכנית בפרויקט כדי שאפשר יהיה
  להמשיך גם בשיחה חדשה.
















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
