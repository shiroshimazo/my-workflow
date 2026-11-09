## What I want

I build systems that should be easy to understand, safe to use, and easy to change later. Code is read far more often than it is written, so write it for the next reader.

## The qualities that matter

- **Readability**: a new reader understands the code without asking me.
- **Clarity**: the obvious solution beats the clever one.
- **Maintainability**: changing one thing should not break five others.
- **No unnecessary code**: every line has a reason to exist.
- **Security**: data is protected and access is controlled from the start, not added later.

## Naming convention

### File names

- Code files use **PascalCase**: `LoginButton`, `UserService`, `InventoryTable`.
- One main thing per file, and the file name matches what the file contains.

### Names inside code

- Name = **purpose + type**, in that order: `loginButton`, `searchInput`, `userForm`, `orderList`, `deleteModal`.
- Classes, components, and types use PascalCase (`LoginButton`). Variables, instances, and functions use camelCase (`loginButton`, `handleLoginClick`).
- Keep names **aligned**: one concept uses the same words everywhere (file `LoginButton`, component `LoginButton`, variable `loginButton`, style class `login-button`). Only the casing changes to fit the language.
- One concept, one name. Do not mix `loginButton`, `loginBtn`, and `signInButton` for the same thing.
- Name by what it is for, not how it looks: `submitOrderButton`, not `blueButton`.

## Semantic code

Semantic code clearly communicates its meaning, purpose, and intent, rather than just its structural appearance or basic syntax.

In practice:

- Names describe purpose and intent: `isEmailValid`, not `check`; `submitOrderButton`, not `btn2`.
- Use elements and structures that carry meaning. On the web, use `<button>`, `<nav>`, `<form>`, `<main>`, and `<label>` instead of generic `<div>` or `<span>` with click handlers.
- The code should answer "why does this exist?" without needing a comment.

Example:

```html
<!-- Not semantic: structure only, no meaning -->
<div class="box blue" onclick="go()">Login</div>

<!-- Semantic: purpose is clear -->
<button type="submit" id="loginButton">Login</button>
```

## Priority when rules conflict

1. Security
2. Correctness
3. Clarity and readability
4. Maintainability
5. Brevity and performance

## Mindset

- Build exactly what was asked, no more, no less.
- If something is unclear or risky, ask before building.
- Be honest: tell me about problems, trade-offs, and things you are unsure about.