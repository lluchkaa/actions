# Assign Author

Assigns an issue or pull request to its author when opened, unless the author is a bot or it already has an assignee. Available as a composite action or a callable workflow wrapping it.

## Usage

### Composite action

```yaml
name: Assign Author

on:
  pull_request:
    types: [opened, reopened]
  issues:
    types: [opened, reopened]

permissions:
  issues: write
  pull-requests: write

jobs:
  assign-author:
    runs-on: ubuntu-latest
    steps:
      - uses: lluchkaa/actions/assign-author@main
```

### Callable workflow

```yaml
name: Assign Author

on:
  pull_request:
    types: [opened, reopened]
  issues:
    types: [opened, reopened]

permissions:
  issues: write
  pull-requests: write

jobs:
  assign-author:
    uses: lluchkaa/actions/.github/workflows/assign-author.yaml@main
    secrets: inherit
```

### Inputs

Neither the action nor the workflow has direct inputs.

### Secrets

| Name           | Description                                                                  |
|----------------|-------------------------------------------------------------------------------|
| `GITHUB_TOKEN` | Automatically provided by GitHub Actions. Used to assign the author.          |

### Outputs

Neither the action nor the workflow produces outputs.

### Description

When an issue or pull request is opened, this assigns its author as an assignee, unless:

- the author is a bot, or
- it already has an assignee.

This keeps ownership visible without requiring authors to remember to assign themselves.
