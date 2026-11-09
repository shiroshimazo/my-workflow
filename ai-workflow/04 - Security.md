Security is part of every task, not an extra step. If you are unsure, choose the safer option and tell me.

## Input

- Treat all external input as untrusted: forms, URLs, headers, files, API requests.
- Validate type, format, length, and allowed values on the server. Client checks are only for convenience.
- Escape or sanitize output to prevent XSS.

## Database

- Use parameterized queries or prepared statements only. Never build queries by joining strings.
- Give the app's database user only the permissions it needs.

## Authentication and authorization

- Check **authentication** (who are you?) and **authorization** (are you allowed?) on every protected route and action, on the server side.
- Never rely on hiding buttons or pages in the UI.
- Check ownership: a user must not read or change another user's data by changing an ID.
- Hash passwords with a strong algorithm (bcrypt, argon2). Never store or log plain passwords.
- Use secure session or token handling, with expiry.

## Secrets and sensitive data

- Never hardcode secrets, keys, or passwords. Use environment variables.
- Never commit `.env` files. Keep them in `.gitignore`.
- Collect and store only the data the system needs.
- Never log passwords, tokens, or personal data.

## Errors and logging

- Show users generic error messages. Keep technical details in server logs.
- Do not expose stack traces, file paths, or query details to users.

## Files and requests

- Validate uploaded file type and size. Store uploads outside executable paths.
- Add rate limiting on login and other sensitive endpoints.
- Use HTTPS and proper CORS settings. Do not use wildcard origins in production.

## Dependencies

- Do not add packages that are unmaintained or unknown.
- Mention known risks when you suggest a dependency.