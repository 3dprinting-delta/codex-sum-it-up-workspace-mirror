# Codex Sum It Up Workspace Mirror

This repository is the umbrella GitHub index for the `C:\codex sum it up` workspace.

It is intentionally lightweight:

- It does not duplicate the full source of each migrated project.
- It acts as the canonical directory of project repositories.
- It documents which GitHub repo should be used as the future deploy portal for each project.
- It carries the GitHub Pages rollout inventory and the standalone microsites for source-only repos.

The machine-readable inventory lives in `project-index.json`.

## GitHub Pages Artifacts

- `github-pages-inventory.json`: per-project GitHub Pages URL, publish mode, and branch source
- `pages-landing/`: tracked landing-page sources for repos that cannot run as full GitHub Pages apps
- `microsites/`: standalone static sites for source-only repos

## Future Deploy Flow

Use the project-specific GitHub repository as the source of truth for any future deployment.

- Frontend and static projects: connect the GitHub repo to the chosen frontend host.
- Node backends and proxies: connect the GitHub repo to the chosen Node host.
- Python services: connect the GitHub repo to the chosen Python-capable host.
- Upstream mirrors and tooling repos: treat GitHub as the source mirror unless a separate deploy target is needed later.

## GitHub Pages Model

The public URL model for this portfolio is now:

- `https://3dprinting-delta.github.io/<repo>/`

Each project is published in one of three ways:

- `pages_direct_publish`: the real static app/site is published on GitHub Pages
- `render_runtime_with_pages_redirect`: GitHub Pages is the public entry URL and should redirect once the real Render runtime URL is available
- `pages_microsite_only`: a standalone GitHub Pages microsite exists for source-only or portfolio-only repos

## Private Repo Constraint

Most migrated project repos are private, and the current GitHub account plan does not support GitHub Pages directly on those private repositories.

To keep the required public URL shape, the live Pages delivery now runs through the public user-site repository:

- `https://github.com/3dprinting-delta/3dprinting-delta.github.io`

That user-site repository serves every project under its own subpath:

- `https://3dprinting-delta.github.io/<repo>/`

At the moment:

- clearly static browser projects are served directly from that user-site repo
- runtime-backed projects still need Render deployment before their `github.io` pages can become real redirects
