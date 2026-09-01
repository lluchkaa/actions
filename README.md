# lluchkaa/actions

Reusable GitHub Actions and workflows.

## Versioning

Each action is versioned with its own git tags (independent of other components):

| Pin | Tag example | When to use |
|-----|-------------|-------------|
| Major line | `auto-assign-pr-v1` | Latest compatible release within major version 1 |
| Minor line | `auto-assign-pr-v1.0` | Latest patch within minor version 1.0 |
| Exact | `auto-assign-pr-v1.0.0` | Pin to a specific release |

Reference tags in workflow `uses:` (`lluchkaa/actions/<path>@<tag>`).

## Actions

| Path | Description |
|------|-------------|
| [auto-assign-pr](auto-assign-pr/README.md) | Callable workflow to assign PR author on open |
