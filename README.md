# Cademí for developers

This is the public place to report bugs, request features, and ask questions about the **[Cademí API v3](https://cademi.dev/api)** and the **[cademi CLI](https://cademi.dev/cli)**. The documentation lives at **[cademi.dev](https://cademi.dev)**.

```sh
curl -fsSL https://cli.cademi.dev/install.sh | bash   # install the CLI (macOS, Linux)
export CADEMI_API_KEY=ck_test_...                     # authenticate without a browser
cademi products list --json                           # every API operation is a command
cademi commands --brief --json                        # list all commands
cademi bug                                            # report a CLI problem
```

**AI agents:** read [AGENTS.md](AGENTS.md).

## Report a problem

| You want to | Go to |
|---|---|
| Report an API bug (an endpoint, status, error, field, or event that does not match the docs) | [API bug report](https://github.com/minhacademi/developers/issues/new?template=api_problem.yml) |
| Report a CLI bug | Run `cademi bug`, or [open a CLI bug report](https://github.com/minhacademi/developers/issues/new?template=bug_report.yml) |
| Report an install or update problem | [Install or update problem](https://github.com/minhacademi/developers/issues/new?template=install_update.yml) |
| Request a feature for the API or the CLI | [Feature request](https://github.com/minhacademi/developers/issues/new?template=feature_request.yml) |
| Fix or improve the documentation | [Documentation problem](https://github.com/minhacademi/developers/issues/new?template=documentation.yml) |
| Ask how to do something | [Discussions](https://github.com/minhacademi/developers/discussions) |
| Report a security vulnerability | [Private report](https://github.com/minhacademi/developers/security/advisories/new), never a public issue |
| Get help with your account, plan, or data | Cademí support |

Include the `request_id` of any API error: it lets Cademí find the call without any other data. See [CONTRIBUTING.md](CONTRIBUTING.md) for what goes where. Please write issues and discussions in English.

Issues are public. Never paste an API key (`ck_live_...`, `ck_test_...`), an access token, a signing secret, or personal data of your users.

## Install the CLI

macOS and Linux:

```sh
curl -fsSL https://cli.cademi.dev/install.sh | bash
```

Windows (PowerShell):

```powershell
irm https://cli.cademi.dev/install.ps1 | iex
```

The CLI keeps itself up to date. To update now, run `cademi update`. See [Installation](https://cademi.dev/cli/installation).

## Release notes

- API: [cademi.dev/api/changelog](https://cademi.dev/api/changelog)
- CLI: [CHANGELOG.md](CHANGELOG.md)
