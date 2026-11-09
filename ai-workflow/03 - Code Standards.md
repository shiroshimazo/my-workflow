## Naming

- Names say what a thing is or does: `getUserById`, not `getData`.
- No cryptic abbreviations. Booleans read like questions: `isActive`, `hasAccess`.
- Follow the naming convention in `01-introduction.md` (PascalCase files, purpose + type names, semantic code).

## Functions and structure

- One function, one job. Aim for under ~30 lines.
- Keep nesting shallow (2-3 levels). Use early returns to avoid deep `if` chains.
- Group code by responsibility (for example: routes, services, data access). Keep each layer in its own place.
- Keep files focused. Split a file when it does more than one thing.

## No unnecessary code

- No unused imports, variables, functions, or files.
- No commented-out code and no leftover debug output.
- No "just in case" features or abstractions. Build for today's need.
- No duplicated logic. Extract it once and reuse it.

## Clarity

- Prefer simple, direct solutions over clever ones.
- No magic numbers or strings. Use named constants.
- Keep configuration (URLs, limits, settings) in one place, not scattered.

## Comments

- Explain **why**, not **what**. The code should show what.
- Document anything non-obvious: business rules, workarounds, trade-offs.

## Error handling

- Handle errors explicitly. Never swallow them silently.
- Fail early with a clear message.
- Handle edge cases: empty values, missing data, invalid input.

## Dependencies

- Use well-maintained libraries only when they clearly save effort.
- Prefer the standard library or what the project already uses.