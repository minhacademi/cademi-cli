# CLI changelog

Release notes of the `cademi` CLI. API release notes: https://cademi.dev/api/changelog

## 0.1.5 - 2026-09-26

- `cademi auth login --platform <address>` goes straight to your account's platform instead of the platform selector in the browser. The address is saved in the profile, reused on the next login, and shown by `cademi auth status` and `cademi env`.
- Human login checks the `iss` parameter returned by the authorization (RFC 9207). It rejects a response whose `iss` does not match the issuer, or that has no `iss` when the server announces support for it.
- Choosing Deny in the browser ends the login right away, without saving anything.
- When the platform refuses the administrator, the login ends right away with the reason: `mfa_required` (two-factor authentication is not turned on), `account_not_eligible` (the account cannot authorize the CLI), or `platform_mismatch` (the administrator belongs to another platform; the message suggests `--platform`).
- The base URL prompt is now "Cademí API URL". Clearer messages while waiting for the browser and for credentials that require human mode.
- Built for API release 3.4.7.

## 0.1.4 - 2026-09-25

- `cademi bug --api` opens the API bug report instead of the CLI one, with `--endpoint` and `--request-id` filled in. `--request-id` also works for CLI bugs.
- Issues now go to this repository, `minhacademi/developers`, which takes reports for both the API and the CLI.
- Built for API release 3.4.5.
- Mutually exclusive flags exit with code `2`.

## 0.1.3 - 2026-09-25

- `cademi commands` lists every command in one call, with the API route, permission, arguments, and flags. `--json` for scripts and AI agents, `--brief` for a small index, and a prefix narrows the list (`cademi commands products`).

## 0.1.2 - 2026-09-25

- `cademi bug` opens a new issue in this repository with your CLI version, platform, and settings filled in. Nothing is sent until you submit it in the browser. `--print` prints the URL instead.
- `--all` now works on every paginated list, including users, enrollments, access schedules, comments, and questions.
- `cademi api` keeps query parameter names as written, such as `tag_id[]`.
- A missing credential exits with code `3`, like other authentication errors.

## 0.1.1 - 2026-09-25

- `cademi env` shows the effective settings and where each value comes from (flag, environment variable, config file, profile, keychain, or default). `cademi env <name>` prints a single value.

## 0.1.0 - 2026-09-25

First release.

- Every API v3 operation as a command, with the API route, permission, and body fields in `--help`.
- Human sign-in (OAuth in the browser plus a credential) and autonomous mode (credential only), with profiles and secrets in the operating system keychain.
- `cademi api`, `cademi listen` (with signed forwarding to a local endpoint), `cademi config validate/plan/apply`, `cademi sandbox reset/run`, `cademi upload`, `cademi download`, `cademi operations wait`, and `cademi doctor`.
- Output as a table, JSON, YAML, or filtered with `--jq`, and stable exit codes.
- Installers for macOS, Linux, and Windows, and signed automatic updates.
