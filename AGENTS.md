# cademi CLI: guide for AI agents

`cademi` is the command-line tool for the Cademí API v3 (an LMS). Every API operation is a command. This file is the short version; the full guides are at https://cademi.dev/cli, and every page is also available as Markdown (append `.md`, for example https://cademi.dev/cli/commands.md). Index for LLMs: https://cademi.dev/llms.txt.

## Quick facts

- Install without prompts: `curl -fsSL https://cli.cademi.dev/install.sh | bash` (macOS, Linux; installs to `~/.cademi/bin`, no sudo). Windows: `irm https://cli.cademi.dev/install.ps1 | iex`.
- Authenticate without a browser: `export CADEMI_API_KEY=ck_test_...` (a sandbox credential; `ck_live_...` is production). No profile or keychain is needed. Optional: `CADEMI_BASE_URL` (default `https://api.cademi.com.br`).
- Every API operation is a command: operationId `products.modules.list` → `cademi products modules list`. Path parameters are positional arguments; query parameters are flags.
- Anything not covered by a command: `cademi api <METHOD> /<path>` (path relative to `/api/v3`).
- Disable automatic updates in unattended runs: `CADEMI_DISABLE_AUTOUPDATE=1` (already off when `CI` is set).

## Discover commands cheaply

```sh
cademi commands --brief --json          # index: command, method, route, summary, args (~90 KB)
cademi commands products --json         # full detail for one group: flags, permissions, operationId
cademi products update --help           # one command: route, permission, body fields
```

In `cademi commands --json`, flags shared by many commands are described once under `flag_sets` (`output`, `body`, `async`, `pagination`, `confirm`, `idempotency`); each command lists the sets it accepts plus its own flags.

## Run without prompts

- Destructive commands ask for confirmation. Pass `--yes` (deletes, `config apply`, `sandbox reset`). Without a terminal and without `--yes`, they exit with code `2`.
- Request body: `-f name=value` (string), `-F name=true|123|null|<json>` (typed), `-d '<json>'` or `-d @file.json`. Nested keys: `-f content.header=...`; arrays: `-f 'tags[]=a'`.
- Writes carry an `Idempotency-Key` and are retried automatically on `429`, `500`, `502`, `503`, `504` and network errors. To retry safely across runs, pass the same `--idempotency-key`.
- `202` responses are operations: add `--wait` to block until they finish.
- Lists return one page; `--all` follows the cursor.

## Read results

- Output is JSON when stdout is not a terminal. Force it with `--json`, or filter with `--jq '<expr>'`.
- With `--json`, `-o json` or `--jq`, errors go to stderr as `{"error":{"code","message","request_id","details"}}`. Branch on `error.code`, never on the message.
- `cademi env` shows the effective settings and where each value comes from; `cademi doctor` checks connectivity, credentials and version compatibility.

## Exit codes

| Code | Meaning |
|---|---|
| 0 | success |
| 1 | generic error, failed operation |
| 2 | invalid usage, or a confirmation needs `--yes` |
| 3 | authentication: 401, no credential configured, or an expired OAuth session |
| 4 | permission (403) |
| 5 | not found (404) |
| 6 | other 4xx: validation, conflict, precondition |
| 7 | rate limited (429, after retries) |
| 8 | server error (5xx, after retries) |
| 130 | canceled |

## Report a problem

- Run `cademi bug --print`. It prints a prefilled issue URL for this repository with the CLI version, platform and settings (no secrets). A person reviews and submits it.
- With the GitHub CLI: `gh issue create -R minhacademi/cademi-cli --label bug --title "..." --body "..."`, including the command, its output, `cademi version` and `cademi env`.
- Write in English. Never include an API key, an access token, a signing secret, or personal data of users. Security vulnerabilities go to the private report (see [SECURITY.md](SECURITY.md)). Problems with the API itself or an account go to Cademí support.
- This repository does not accept pull requests; see [CONTRIBUTING.md](CONTRIBUTING.md).

## Do not

- Run `cademi auth login` in an unattended session: it waits for a browser. Use `CADEMI_API_KEY`.
- Use a production credential (`ck_live_...`) to experiment. Use a sandbox credential (`ck_test_...`); `cademi sandbox reset --yes` restores the sandbox data.
- Print or log `CADEMI_API_KEY`. `--debug` logs requests without secrets.
