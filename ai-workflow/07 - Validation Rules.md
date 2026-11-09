Every form and every piece of user input must be validated. Never accept bad data, and always tell the user exactly what to fix. This applies to all forms: sign up, login, product forms, search, settings, and any other input.

## Core rules

- Validate on **both** sides. Client-side validation gives fast feedback. **Server-side validation is the real protection** and is required (see `04-security.md`). Never trust the client alone.
- **Required means required.** If any required field is empty, block the submit and show an error for each empty field.
- **Not empty is not valid.** Check type, format, length, and allowed values. Junk like `1` in every field must be rejected.
- Trim spaces first. A field with only spaces counts as empty.
- If the data is wrong, it is never saved.

## How to show errors

- **Highlight each invalid field** with a red border and an error icon. Do not rely on color alone.
- Show a **short message under the field** that says what is wrong and what to change.
- On submit with errors, also show a pop-up or notification such as `Please fix the highlighted fields.`
- Move focus to the first invalid field.
- Keep what the user typed. Never clear the whole form because of an error. (Never re-fill password fields from the server.)
- Clear an error as soon as the user fixes that field.
- Error text follows `05-design-rules.md`: concise, short, direct.

### Message pattern

Say what is wrong and how to fix it.

|Bad|Good|
|---|---|
|`Invalid input`|`Username must be 3-20 characters.`|
|`Error`|`Enter a valid email, like name@example.com.`|
|`Wrong password` (on sign up)|`Password must be at least 8 characters.`|

## When to validate

- **On blur** (when the user leaves a field): check that field.
- **On submit**: check all fields together and show every error at once, not one by one.
- Do not show errors on a field the user has not touched yet.
- Do not disable the submit button without explaining why. Let the user click it and see what is wrong.
- Disable the button only while the request is in progress, to prevent double submits.

## Server errors

- Show server errors next to the field they belong to (for example `Username is already taken.`).
- For login and password reset, use one generic message: `Incorrect username or password.` Do not reveal which part was wrong or whether an account exists.
- Never show technical details to the user.

## Example: sign up form

|Field|Rules|Example message|
|---|---|---|
|Username|Required. 3-20 chars. Letters, numbers, underscore only. Starts with a letter. Not already taken.|`Username must be 3-20 characters and start with a letter.`|
|Full name|Required. 2-60 chars. Letters from any language, spaces, hyphens, apostrophes. Must contain a letter.|`Enter your full name.`|
|Email|Required. Valid email format. Max 254 chars. No spaces. Not already used.|`Enter a valid email, like name@example.com.`|
|Password|Required. At least 8 chars. Reject common or trivial passwords (`11111111`, `password`) and a password equal to the username or email.|`Password must be at least 8 characters.`|
|Confirm password|Required. Must match password.|`Passwords do not match.`|

Notes:

- A format check cannot prove an email is real. For example, `1@gmail.com` passes a format check, but Gmail addresses need at least 6 characters before the `@`, so it cannot exist. Add a provider-specific rule only if you accept it may need updating. The reliable check is a **verification email** the user must confirm before the account is active.
- Show a password strength hint while the user types.

## Common field types

|Type|Rules|
|---|---|
|Number / quantity|Must be a number. Set min and max. No negatives unless allowed. Whole numbers only when counting items.|
|Text / name|Required or optional, min and max length, allowed characters.|
|Date|Valid date, in an allowed range.|
|Select / option|Value must be one of the allowed options.|
|File upload|Allowed type, max size, checked on the server.|
|Free text|Max length. Escape output to prevent XSS.|

## Required tests

After building or changing a form, test at least these cases and confirm each is handled:

1. All fields empty, then submit.
2. Only some fields filled (for example only the username).
3. Every field set to `1`.
4. Email missing `@` or domain (`abc`, `abc@`, `abc@gmail`).
5. Password and confirm password do not match.
6. Fields with only spaces.
7. Very long input.
8. Special characters and script text (`<script>alert(1)</script>`).
9. All fields valid, which must succeed.

For each failing case, check that the invalid field is highlighted red, the message says what to change, and nothing invalid is saved. State in your report which cases you tested.