# Contributing

Thanks for helping improve the Cademí API and the `cademi` CLI. Their source code is maintained by Cademí elsewhere, so this repository does not accept pull requests. It is the place for reports, requests, and questions.

Issues and discussions are in English, so everyone who integrates with Cademí can follow them.

## Where to go

| You want to | Go to |
|---|---|
| Report an API bug | [API bug report](https://github.com/minhacademi/developers/issues/new?template=api_problem.yml) |
| Report a CLI bug | Run `cademi bug`, or [open a CLI bug report](https://github.com/minhacademi/developers/issues/new?template=bug_report.yml) |
| Report an install or update problem | [Install or update problem](https://github.com/minhacademi/developers/issues/new?template=install_update.yml) |
| Request a feature | [Feature request](https://github.com/minhacademi/developers/issues/new?template=feature_request.yml) |
| Fix or improve the guides | [Documentation problem](https://github.com/minhacademi/developers/issues/new?template=documentation.yml) |
| Ask how to do something | [Discussions, Q&A](https://github.com/minhacademi/developers/discussions/categories/q-a) |
| Report a security vulnerability | [Private report](https://github.com/minhacademi/developers/security/advisories/new), never a public issue |
| Get help with your account, plan, or data | Cademí support |

## API or CLI?

If the API returns something that contradicts the documentation, it is an API bug, even when you call it through the CLI. Check with `cademi api <METHOD> <path> --debug` (or any HTTP client): if the raw response is wrong, open an API bug report. If the response is right but the CLI shows or handles it wrong, open a CLI bug report.

## A good report

- The exact request or command, what you expected (with a link to the documentation), and what happened.
- The `request_id` of any API error. It is in the error body and in the `X-Request-Id` header.
- The API release (`X-Cademi-Release` header) or the CLI version (`cademi version`). `cademi bug` fills in the CLI version and `cademi env` for you.
- For the CLI, the output with `--debug`. Secrets are never logged, but remove anything else sensitive.

Issues and discussions are public. Never paste an API key (`ck_live_...`, `ck_test_...`), an access token, a signing secret, or personal data of your users.
