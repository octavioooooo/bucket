# AGENTS

## Repository type
This repository is a Scoop bucket root. The package manifest files live under `bucket/`, and this repo is not a general application source tree.

## Key file
- `bucket/byond.json` — Scoop manifest for the `byond` package.

## What AI agents should know
- Do not assume a typical app build/test workflow. There are no frontend, backend, or runtime source files here.
- Changes should focus on Scoop manifest maintenance, package metadata, installer behavior, and update rules.
- Preserve Scoop manifest schema structure and quoting conventions.

## Manifest-specific conventions
- `url`, `hash`, `extract_dir`, `bin`, `persist`, `env_add_path`, and `post_install` are package-specific manifest fields.
- `suggest` is used to recommend optional dependencies.
- `checkver` and `autoupdate` define update discovery and automatic manifest bumps.
- `installer_success_codes` can include nonzero exit codes that are still successful for this installer.

## Validation guidance
- Prefer validating against Scoop manifest schema and known Scoop conventions.
- Do not invent build or test commands for this repo unless additional tooling is added.

## When asked to improve the repo
- Focus on adding or updating bucket manifest files under `bucket/`.
- Keep documentation minimal and accurate; this repo is mainly a package manifest repository.

## Pushing updates to Scoop
- This repo appears to be a Scoop bucket. To contribute updates, create a pull request against the target Scoop bucket repository.
- For a new package manifest, scaffold a template with Scoop:
  - `cd c:\Users\octavio\PROJECTS\buckets`
  - `scoop create bucket\<package>.json`
- For existing package updates, edit the manifest file under `bucket/`.
- Validate the manifest before opening the PR:
  - Ensure JSON is valid.
  - Follow Scoop schema conventions and manifest field style.
  - Optionally test locally with the manifest path, e.g. `scoop install .\bucket\byond.json`.
- If this repository is a fork of `ScoopInstaller/Bucket`, the likely flow is:
  1. Update or create `bucket/<name>.json`.
  2. Commit with a descriptive message, e.g. `byond: update to 516.1681`.
  3. Push the branch to the fork.
  4. Open a pull request against `ScoopInstaller/Bucket` or the configured upstream bucket repo.
- Do not merge package changes without validating that the manifest passes Scoop bucket review expectations and any CI checks.
