# action-run-e2e-tests
This GH Action is intended to encapsulate logic for running end-to-end tests (written in [Cypress](https://docs.cypress.io/)) with [Currents dev](https://currents.dev/#faq) platform for [parallelization](https://docs.cypress.io/guides/guides/parallelization).

## Input description

| Script       | Description                                                                                                                                                                                                         |
|--------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| github_token | Access token                                                                                                                                                                                                        |
| url          | Name of the env where tests will be running. You should follow next convention in order to have correct `baseUrl` setup. Example: `dev -> url of dev env; custom -> url which will be proceeded to customUrl input` |
| customUrl    | Url of custom env (PR deploy, dev/prod env). You need set `url` to `custom` in order to run tests against this url.                                                                                                 |
| spec_file    | [Pattern string](https://docs.cypress.io/guides/guides/command-line#cypress-run-spec-lt-spec-gt) which points Cypress what spec files to run.                                                                       |
| tags         | Tags necessary to run specific tests with [cypress-grep](https://github.com/cypress-io/cypress-grep) plugin (tests for comp-plex, key_info,rent_comps and etc).                                                     |
| ref          | Ref param for [action/checkout](https://github.com/actions/checkout#usage).                                                                                                                                         |
| secret_name  | Name of the secret in aws secret manager                                                                                                                                                                            |