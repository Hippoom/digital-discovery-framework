# Digital Discovery Framework

This repository is the **public GitHub Pages release artifact** for the Digital Discovery Framework:

<https://hippoom.github.io/digital-discovery-framework/>

## Source and release boundary

The canonical Markdown, Portal manifest, source validation, and build tooling are maintained outside this repository in the private Digital Discovery workspace. This repository contains **only** the audited static output of the Portal public profile.

Do not copy any of the following into this repository:

- canonical Obsidian Markdown sources;
- `Case Validation` or historical material;
- internal maintainer pages, Portal contracts, or local automation;
- external-vault material, local paths, `.venv`, `.portal-build`, or source-workspace configuration.

## Publish an approved Portal update

From the private source workspace:

```bash
make portal-release-build
make portal-test
```

`portal-release-build` builds for the GitHub Pages project path, runs `mkdocs build --strict`, and audits the final static site for broken paths, routes, anchors, excluded content, and raw Markdown URLs.

Only after these checks pass, replace this repository’s publishable files with the audited `site/` directory contents, review the release-repository diff, then commit and push `main`.

GitHub Actions deploys the repository root to GitHub Pages on each push to `main`.
