# Contributing

Thanks for helping improve the `cademi` CLI. The CLI source code is maintained by Cademí in a separate repository, so this repository does not accept pull requests. It is the place for reports, requests, and questions.

## Where to go

| You want to | Go to |
|---|---|
| Report a bug | Run `cademi bug`, or [open a bug report](https://github.com/minhacademi/cademi-cli/issues/new?template=bug_report.yml) |
| Report an install or update problem | [Install or update problem](https://github.com/minhacademi/cademi-cli/issues/new?template=install_update.yml) |
| Request a feature | [Feature request](https://github.com/minhacademi/cademi-cli/issues/new?template=feature_request.yml) |
| Fix or improve the guides | [Documentation problem](https://github.com/minhacademi/cademi-cli/issues/new?template=documentation.yml) |
| Ask how to do something | [Discussions, Q&A](https://github.com/minhacademi/cademi-cli/discussions/categories/q-a) |
| Report a security vulnerability | [Private report](https://github.com/minhacademi/cademi-cli/security/advisories/new), never a public issue |
| Get help with the API, your account, or its data | Cademí support |

## A good bug report

- The exact command, what you expected, and what happened.
- The output with `--debug` when the problem involves the API. Secrets are never logged, but remove anything else sensitive.
- The `request_id` of any API error.
- Your environment. `cademi bug` fills in the output of `cademi version` and `cademi env` for you.

Issues and discussions are public. Never paste an API key (`ck_live_...`, `ck_test_...`), an access token, a signing secret, or personal data of your users.
