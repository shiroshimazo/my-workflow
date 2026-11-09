## Mandatory first step (every prompt, no exceptions)

Before writing, editing, or deleting any code, you MUST read every file in `ai-workflow/` in this order:

1. `ai-workflow/00-README.md`
2. `ai-workflow/01-introduction.md`
3. `ai-workflow/02-process.md`
4. `ai-workflow/03-code-standards.md`
5. `ai-workflow/04-security.md`
6. `ai-workflow/05-review-checklist.md`
7. `ai-workflow/06-design-rules.md`
8. `ai-workflow/07-validation-rules.md`

Re-read them at the start of every new prompt, even if you read them earlier in this session. Do not rely on memory of earlier reads. If any file is missing or unreadable, stop and tell me instead of continuing.

## Confirm before coding

Start your first reply to each prompt with:

`Workflow read: 00-07 ✔`

Then give a short plan before changing anything. If you did not read all the files, do not write code.

## While working

- Follow the workflow files over your own defaults. If a rule conflicts with my prompt, tell me and ask.
- Priority when rules conflict: security, correctness, clarity, maintainability, then brevity and performance.
- Build only what I asked. No extra features and no "just in case" code.
- Work in small steps, one change at a time.
- Ask before deleting files, dropping data, or adding dependencies.

## Before you finish

1. Run your work against `ai-workflow/05-review-checklist.md`.
2. End with a short report: what changed, which files, why, what to test, and any assumptions or risks.
3. Say which checklist items you could not verify.