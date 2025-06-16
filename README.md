# Rebuild package-lock.json

This composite GitHub Action automatically

- rebuild the `package-lock.json` file to upgrade transitive dependencies
- creates a pull request to review the changes

Dependabot runs from Monday to Friday so worth to run this job on Saturday and merge the PR on Sunday to decrease the CI
jobs / costs.

## Action inputs

All inputs are optional. If not set, sensible defaults will be used.

| Name              | Description                                                                                                                                                                                          | Default                                                          |
|-------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------|
| token             | The token that the action will use to create and update the pull request. See [token of create-pull-request](https://github.com/peter-evans/create-pull-request/tree/main?tab=readme-ov-file#token). | `GITHUB_TOKEN`                                                   |
| node-version      | See [node-version of setup-node](https://github.com/actions/setup-node#usage)                                                                                                                        |                                                                  |
| node-version-file | See [node-version-file of setup-node](https://github.com/actions/setup-node#usage)                                                                                                                   | `.nvmrc`                                                         |
| commit-message    | The message to use when committing changes. It will be the title of the PR too                                                                                                                       | fix: rebuild package-lock.json to upgrade transient dependencies |
