# pipeline-test-fixture

A test fixture repo for `blackbrowedlabs.com`'s release pipeline. Not a
real product; exists only to verify the conventions doc + loader against
real GitHub Releases data.

## What this repo does

Each tagged release here triggers a `repository_dispatch` to the website
repo, which causes a fresh deploy. The website's loader fetches this
repo's releases and surfaces them on `/produkte/pipeline-test-fixture/`
(dev only — the products entry has `draft: true`).

## How to release

See `docs/PRODUCT_REPO_CONVENTIONS.md` in `blackbrowed-labs/blackbrowedlabs.com`
for the full conventions. TL;DR:

1. Edit `CHANGELOG.md` — add a new `## [vX.Y.Z] — YYYY-MM-DD` section.
2. Tag: `git tag -a vX.Y.Z -m "vX.Y.Z"` and push.
3. Workflow auto-creates the GitHub Release and dispatches the rebuild.
