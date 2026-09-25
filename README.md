# cademi

`cademi` is the command-line tool for the [Cademí API v3](https://cademi.dev/api). It runs every API operation as a command, signs in as an administrator or with a credential alone, forwards events to your local application, and applies declarative configuration to your account.

This repository is where you report bugs, request features, and ask questions about the CLI. The documentation lives at **[cademi.dev/cli](https://cademi.dev/cli)**.

## Install

macOS and Linux:

```sh
curl -fsSL https://cli.cademi.dev/install.sh | bash
```

Windows (PowerShell):

```powershell
irm https://cli.cademi.dev/install.ps1 | iex
```

The CLI keeps itself up to date. To update now, run `cademi update`. See [Installation](https://cademi.dev/cli/installation).

## Get started

```sh
cademi auth login
cademi products list --limit 5
cademi --help
```

## Report a problem

Run `cademi bug`. It opens a new issue here with your CLI version, platform, and settings already filled in. Review the text before you submit it.

- **Bugs and feature requests:** [open an issue](https://github.com/minhacademi/cademi-cli/issues/new/choose).
- **Questions and ideas:** [Discussions](https://github.com/minhacademi/cademi-cli/discussions).
- **Security vulnerabilities:** never in a public issue. See [SECURITY.md](SECURITY.md).
- **A problem with the API itself** (an endpoint, your account, or your data): contact Cademí support.

Issues are public. Never paste an API key (`ck_live_...`, `ck_test_...`), an access token, a signing secret, or personal data of your users.

## Release notes

See [CHANGELOG.md](CHANGELOG.md).
