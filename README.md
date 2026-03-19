# KeystoneLoot-Mirror

Mirror of [KeystoneLoot by redpril](https://github.com/redpril/KeystoneLoot) for use with WowUp.

## How the mirror works

A scheduled GitHub Actions workflow (`.github/workflows/sync-upstream.yml`) runs
daily at 06:00 UTC and can also be triggered manually via **Actions → Run workflow**.

It uses a git-based content-sync strategy:

1. Adds `redpril/KeystoneLoot` as an `upstream` remote and fetches `master`.
2. Checks out all upstream files into this repository's working tree.
3. Restores repo-specific files (`README.md`, `.github/`) so they are never
   overwritten by upstream changes.
4. Removes any files that have been deleted from upstream.
5. Commits and pushes only when actual file content has changed — no noisy
   commits when nothing is new.

## Repo-specific files

| Path | Purpose |
|------|---------|
| `README.md` | This file — mirror documentation |
| `.github/workflows/sync-upstream.yml` | Sync workflow |

All other files in this repository are synced directly from the upstream source.
