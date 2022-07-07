# action-run-e2e-tests
This GH Action is intended to encapsulate logic for running end-to-end tests (written in [Cypress](https://docs.cypress.io/)) with [Currents dev](https://currents.dev/#faq) platform for [parallelization](https://docs.cypress.io/guides/guides/parallelization).

## Input description

| Script         | Description                                                                                                                                                                       |
| -------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| github_token            | Access token                                                                                                                                         |
| username      | Username for test run                                                     |
| password       | Password for username                                                        |
| env    | Name of the env where tests will be running. You should follow next convention in order to have correct `baseUrl` setup. Example: `dev -> url of dev env; custom -> url which will be proceeded to customEnv input`                                   |
| customEnv     | Url of custom env (PR deploy, dev/prod env). You need set `env` to `custom` in order to run tests against this url. |
| url          | One of the three env urls we usually use for test runs: `dev`, `stage`, `prod`. These options are predefined.                                                                                                                                                   |
| spec_file          | [Pattern string](https://docs.cypress.io/guides/guides/command-line#cypress-run-spec-lt-spec-gt) which points Cypress what spec files to run.                                                                                                                                                                   |
| tags        | Tags necessary to run specific tests with [cypress-grep](https://github.com/cypress-io/cypress-grep) plugin (tests for comp-plex, key_info,rent_comps and etc).                                                                                                                          |
| record_key    | [Special string](https://currents.dev/readme/guides/record-key) which used to accosiate our test runs with Currents dev platform.                                                                                                                     |
| ref    | Ref param for [action/checkout](https://github.com/actions/checkout#usage).                                                                                                                     |