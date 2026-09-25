# Changelog

## 0.1.1 - 2026-09-25

- `cademi env` shows the effective settings and where each value comes from (flag, environment variable, config file, profile, keychain, or default). `cademi env <name>` prints a single value.

## 0.1.0 - 2026-09-25

First release.

- Every API v3 operation as a command, with the API route, permission, and body fields in `--help`.
- Human sign-in (OAuth in the browser plus a credential) and autonomous mode (credential only), with profiles and secrets in the operating system keychain.
- `cademi api`, `cademi listen` (with signed forwarding to a local endpoint), `cademi config validate/plan/apply`, `cademi sandbox reset/run`, `cademi upload`, `cademi download`, `cademi operations wait`, and `cademi doctor`.
- Output as a table, JSON, YAML, or filtered with `--jq`, and stable exit codes.
- Installers for macOS, Linux, and Windows, and signed automatic updates.
