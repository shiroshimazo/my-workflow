# AI Workflow

A reusable set of Markdown rules for building software with an AI assistant, focused on **code quality**: readable, clear, maintainable, and secure.

Instead of re-explaining your standards in every chat or project, you write them once here and point the AI at this folder.

## Why this exists

AI assistants write code fast, but without clear instructions the result can be messy, over-engineered, or insecure. This workflow gives the AI:

- A clear picture of what good code means to you
- A step-by-step way of working (plan, build small, review, report)
- Concrete rules it can follow and check itself against

## What's inside

```
.
├── README.md
├── LICENSE
└── ai-workflow/
    ├── 00-README.md                     index, read order, how to use
    ├── 01-introduction.md               goals, naming convention, semantic code
    ├── 02-process.md                    how the AI and I work together
    ├── 03-code-standards.md             readability and maintainability rules
    ├── 04-security.md                   protecting data and access
    ├── 05-review-checklist.md           self-check before a task is "done"
    ├── 06-design-rules.md               UI/UX laws and concise interface text
    └── 07-validation-rules.md           form validation and error messages
```

| File | What it covers |
|---|---|
| `01-introduction.md` | The qualities that matter, naming convention, semantic code, and priority order when rules conflict |
| `02-process.md` | Understand, plan, build in small steps, self-review, report |
| `03-code-standards.md` | Function size, structure, no unnecessary code, comments, error handling |
| `04-security.md` | Input validation, queries, authentication and authorization, secrets, logging |
| `05-review-checklist.md` | A checklist the AI runs against its own work before finishing |
| `06-design-rules.md` | Jakob's, Miller's, Hick's, Fitts's laws, Peak-End Rule, Aesthetic-Usability Effect, Occam's Razor, and concise writing |
| `07-validation-rules.md` | Form validation on client and server, red-highlighted fields with clear messages, and required test cases |

## Quick start

1. **Copy the folder** into your project (or keep it in a shared place such as an Obsidian vault).
2. **Create the project context.** Copy `08-project-context-template.md` into your project as `context.md` and fill it in.
3. **Point your AI at it.** At the start of a session, say something like:

   > Read every file in `ai-workflow/` in order, then read `context.md`, before doing anything.

   Most AI coding tools also support a project instruction file (for example `CLAUDE.md`). You can add a single line there that points to this folder so it loads automatically.

4. **Work in small steps.** The AI plans first, builds one change at a time, and reviews its own work against the checklist.

## Core principles

- **Simple over clever.** The obvious solution beats the clever one.
- **Build only what was asked.** No extra features and no "just in case" code.
- **Security from the start.** Validate input, use parameterized queries, check access on every protected action, and never hardcode secrets.
- **One concept, one name.** Names describe purpose and stay consistent everywhere.
- **Design by proven UI/UX laws.** Familiar patterns, few choices, large targets, and short, direct text.
- **Never accept bad data.** Validate every form on the server, highlight what is wrong, and say how to fix it.

When rules conflict, the priority is: security, correctness, clarity, maintainability, then brevity and performance.

## Naming convention

| Thing | Style | Example |
|---|---|---|
| Code file names | PascalCase | `LoginButton`, `UserService` |
| Classes, components, types | PascalCase | `LoginButton` |
| Variables, instances, functions | camelCase | `loginButton`, `handleLoginClick` |

Names follow **purpose + type** (`loginButton`, `searchInput`, `orderList`) and describe what something is for, not how it looks. Code should be **semantic**: it communicates its meaning, purpose, and intent, not just its structure.

## Customizing it

This is a starting point. Make it yours:

- Change any rule that doesn't match how you build.
- When the AI does something you dislike, find the missing rule and add it to the right file.
- Keep project-specific details (stack, libraries, roles) in each project's `context.md`, so the general files stay reusable.

## Limitations

This workflow improves the AI's output, but it doesn't replace review. Always check security-critical code yourself, especially authentication, payments, and permissions.

## License

This project is licensed under the [MIT License](LICENSE).
