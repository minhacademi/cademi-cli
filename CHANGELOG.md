# CLI changelog

Release notes of the `cademi` CLI. API release notes: https://cademi.dev/api/changelog

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
