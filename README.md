# Digital Discovery Framework — Public Release

This repository deploys the audited public Portal to GitHub Pages:

<https://hippoom.github.io/digital-discovery-framework/>

## Repository layout

```text
.github/workflows/deploy.yml  # deployment mechanism
README.md                     # release instructions
.gitattributes               # generated-file policy
public/                       # only generated Portal output is deployed
```

GitHub Actions deploys `public/` on every push to `main`.

## Prepare a release

The canonical Markdown, Portal configuration, checks and build tooling remain in the private Digital Discovery source workspace. Do not copy source Markdown, Cases, maintainer content, Portal tooling, `.venv`, `.portal-build`, local paths or external-vault content into this repository.

From the source workspace, run:

```bash
make portal-release-prepare
```

The command builds and audits the public Portal, verifies this repository’s workflow targets `public/`, then safely synchronizes only the generated site into this repository’s `public/` directory. It never commits or pushes.

Then review and publish:

```bash
cd ~/Workspace/digital-discovery-framework
git status
git diff --stat
git add public .github/workflows/deploy.yml README.md .gitattributes
git commit -m "Publish Portal update"
git push origin main
```
