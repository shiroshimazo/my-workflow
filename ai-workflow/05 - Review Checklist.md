Before saying a task is done, check your own work against this list. If any answer is "no" or "not sure", fix it or tell me.

## Scope

- [ ] Does it do what I asked, and nothing extra?
- [ ] Did I only touch the files needed?
- [ ] No new dependency added without my approval?

## Readability and clarity

- [ ] Are names clear and descriptive?
- [ ] Is each function short and focused on one job?
- [ ] Could a new reader follow it without help?

## Maintainability

- [ ] Is there any duplicated logic?
- [ ] Are constants and config in one place, with no magic values?
- [ ] Does it match the project's structure and style?

## No unnecessary code

- [ ] Any unused imports, variables, functions, or files?
- [ ] Any commented-out code or debug output left behind?

## Correctness

- [ ] Are errors and edge cases handled (empty, missing, invalid)?
- [ ] Did I check that it actually works, or say clearly that I could not?

## Security

- [ ] Is all external input validated on the server?
- [ ] Are queries parameterized?
- [ ] Is authentication AND authorization checked on protected actions?
- [ ] Any secret or sensitive data exposed, hardcoded, or logged?
- [ ] Do error messages avoid leaking internal details?

## Report

- [ ] Did I summarize the changes, risks, and assumptions?
- [ ] Did I suggest a one-line commit message (without running git)?