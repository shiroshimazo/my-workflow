# AI Workflow

A reusable set of Markdown rules for building software with an AI assistant, focused on **code quality** (readable, clear, maintainable, secure) and **interface quality** (usable, modern, minimal).

Instead of re-explaining your standards in every chat or project, you write them once here and point the AI at this folder.

## Why this exists

AI assistants write code fast, but without clear instructions the result can be messy, over-engineered, insecure, or visually generic. This workflow gives the AI:

- A clear picture of what good code means to you
- A step-by-step way of working (understand, plan, build small, review, report)
- Concrete rules it can follow and check itself against
- A visual style that avoids the templated "AI look"

## What's inside

```
.
├── README.md
├── LICENSE
├── AGENTS.md                            copy to your project root
└── ai-workflow/
    ├── 00-README.md                     index, read order, how to use
    ├── 01-introduction.md               goals, naming convention, semantic code
    ├── 02-process.md                    how the AI and I work together
    ├── 03-code-standards.md             readability and maintainability rules
    ├── 04-security.md                   protecting data and access
    ├── 05-review-checklist.md           self-check before a task is "done"
    ├── 06-design-rules.md               UI/UX laws and concise interface text
    ├── 07-validation-rules.md           form validation and error messages
    └── 08-visual-style-rules.md         modern, minimal look and AI-slop blacklist
```

| File                       | What it covers                                                                                                         |
| -------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `AGENTS.md`                | Makes the AI read every workflow file, and confirm it did, before writing code on each prompt                          |
| `01-introduction.md`       | The qualities that matter, naming convention, semantic code, and priority order when rules conflict                    |
| `02-process.md`            | Understand, plan, build in small steps, self-review, report. The AI never runs `git add` or `git commit`              |
| `03-code-standards.md`     | Function size, structure, no unnecessary code, comments, error handling                                                |
| `04-security.md`           | Input validation, queries, authentication and authorization, secrets, logging, uploads                                 |
| `05-review-checklist.md`   | A checklist the AI runs against its own work before finishing                                                          |
| `06-design-rules.md`       | Jakob's, Miller's, Hick's, Fitts's laws, Peak-End Rule, Aesthetic-Usability Effect, Occam's Razor, and concise writing |
| `07-validation-rules.md`   | Form validation on client and server, red-highlighted fields with clear messages, and required test cases              |
| `08-visual-style-rules.md` | Design tokens first, minimal layout and typography, subtle motion, required UI states, and an AI-slop blacklist        |

## Quick start

1. **Copy the folder.** Put `ai-workflow/` into your project (or keep it in a shared place such as an Obsidian vault).
2. **Copy `AGENTS.md`** into your project root. Codex and other agents that support it load it automatically, so the AI reads the whole workflow before writing code on every prompt.
3. **Create `context.md`** in your project root. It holds everything specific to that project, so the workflow files stay reusable:

   ```markdown
   # Project Context
   - Stack: (language, framework, database)
   - Naming exceptions: (stack conventions that override the naming table)
   - Applicable workflow files: (for example, skip 06-08 for an API-only project)
   - Visual direction: (for example, warm neutral, one green accent)
   - Commands: (run, test, lint)
   - Notes: (anything else the AI should know)
   ```

4. **Prompt the task.** You don't need to mention the workflow each time. Describe the task and let `AGENTS.md` do the rest.

Other tools: if your AI tool uses a different instruction file (for example `CLAUDE.md`), add a single line pointing to `ai-workflow/` and `context.md`.

## How to give a task

Use this shape for every prompt:

```
Task: what to build
Where: which file, page, or folder
Details: the content, behavior, and states
Limits: what NOT to do
```

Example:

```
Task: Build the main navigation bar.

Where: src/components/NavigationBar, used in the main layout.

Details:
- Links: Dashboard, Employees, Reports, Settings
- Logo on the left, user menu on the right
- Highlight the active page
- On mobile, collapse into a menu button with a slide-in panel
- Keyboard accessible, with visible focus states

Limits:
- Only the navigation bar. Don't change other pages.
- Use existing design tokens. If none exist, create them first.
- No new dependencies.
```

Tips:

- **One task per prompt.** Small, focused changes give the cleanest results.
- **Check the confirmation line.** Each reply should start with `Workflow read: 00-08 ✔`. If it doesn't, tell the AI to read the workflow first.
- **Ask for a plan on bigger tasks.** "Show your plan and wait for my approval before coding."
- **Review against the checklist.** "Run `05-review-checklist.md` against your work and show the results."
- **Fix with specifics.** If the AI repeats a mistake, find the missing rule and add it to the right file.

## Core principles

- **Simple over clever.** The obvious solution beats the clever one.
- **Build only what was asked.** No extra features and no "just in case" code.
- **Security from the start.** Validate input, use parameterized queries, check access on every protected action, and never hardcode secrets.
- **One concept, one name.** Names describe purpose and stay consistent everywhere.
- **Design by proven UI/UX laws.** Familiar patterns, few choices, large targets, and short, direct text.
- **Never accept bad data.** Validate every form on the server, highlight what is wrong, and say how to fix it.
- **Modern and minimal, never templated.** Define tokens first, remove before adding, and avoid the AI-slop look.
- **You stay in control.** The AI plans first, asks before risky changes, and never commits for you.

When rules conflict, the priority is: security, correctness, clarity, maintainability, then brevity and performance.

## Naming convention

| Thing                           | Style      | Example                           |
| ------------------------------- | ---------- | --------------------------------- |
| Code file names                 | PascalCase | `LoginButton`, `UserService`      |
| Classes, components, types      | PascalCase | `LoginButton`                     |
| Variables, instances, functions | camelCase  | `loginButton`, `handleLoginClick` |

Names follow **purpose + type** (`loginButton`, `searchInput`, `orderList`) and describe what something is for, not how it looks. Code should be **semantic**: it communicates its meaning, purpose, and intent, not just its structure.

If your stack has its own conventions (for example `snake_case` files in Python, or framework-required file names), note them under "Naming exceptions" in `context.md`.

## Works across stacks

The rules describe *how to work*, not a specific language or framework, so they carry over to most projects. Put stack-specific details in each project's `context.md`. For projects without a UI (CLI tools, APIs, scripts), list which workflow files apply so the AI skips the design and visual rules.

## Customizing it

This is a starting point. Make it yours:

- Change any rule that doesn't match how you build.
- When the AI does something you dislike, find the missing rule and add it to the right file.
- Keep project-specific details (stack, libraries, roles, visual direction) in each project's `context.md`.
- If you add a workflow file, also add it to `AGENTS.md` and the file table above.

## Limitations

This workflow improves the AI's output, but it doesn't replace review. An instruction file makes skipping the rules unlikely, not impossible. Always check security-critical code yourself, especially authentication, payments, and permissions.

## License

This project is licensed under the [MIT License](LICENSE).
