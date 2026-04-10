# KeystoneLoot-Mirror

Mirror workflow for [KeystoneLoot by Wolkenschutz](https://github.com/Wolkenschutz/KeystoneLoot) for use with WowUp.

## How the mirror works

A scheduled GitHub Actions workflow (`.github/workflows/sync-upstream.yml`) runs
every 30 minutes and can also be triggered manually via **Actions → Run workflow**.

It keeps this repository trimmed down and pulls the addon directly from the
upstream source repository when a new release is needed:

1. Checks out this mirror repository and the upstream `Wolkenschutz/KeystoneLoot`
   repository.
2. Detects whether the upstream `main` branch is already mirrored by checking
   for a matching release tag.
3. Builds a WowUp-ready ZIP from the upstream addon files.
4. Publishes a GitHub release only when the upstream revision is new.

## Repo-specific files

| Path | Purpose |
|------|---------|
| `README.md` | This file — mirror documentation |
| `.github/workflows/sync-upstream.yml` | Sync workflow |

This repository intentionally keeps only the workflow and this README; the addon
source lives in the upstream repository maintained by Wolkenschutz.
