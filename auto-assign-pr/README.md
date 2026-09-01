# Auto Assign PR Author

Assigns a pull request to its author when it is opened, unless the author is a bot or the PR already has an assignee. Available as a composite action or a callable workflow wrapping it.

## Usage

### Composite action

```yaml
name: Auto Assign PR Author

on:
  pull_request:
    types: [opened]

permissions:
  pull-requests: write

jobs:
  assign-author:
    runs-on: ubuntu-latest
    steps:
      - uses: lluchkaa/actions/auto-assign-pr@main
```

### Callable workflow

```yaml
name: Auto Assign PR Author

on:
  pull_request:
    types: [opened]

permissions:
  pull-requests: write

jobs:
  assign-author:
    uses: lluchkaa/actions/.github/workflows/auto-assign-pr.yaml@main
    secrets: inherit
```

### Inputs

Neither the action nor the workflow has direct inputs.

### Secrets

| Name           | Description                                                                  |
|----------------|-------------------------------------------------------------------------------|
| `GITHUB_TOKEN` | Automatically provided by GitHub Actions. Used to assign the PR author.       |

### Outputs

Neither the action nor the workflow produces outputs.

### Description

When a pull request is opened, this assigns the PR author as an assignee, unless:

- the author is a bot, or
- the pull request already has an assignee.

This keeps ownership visible on PRs without requiring authors to remember to assign themselves.
