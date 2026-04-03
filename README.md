# Codex Sum It Up Workspace Mirror

This repository is the umbrella GitHub index for the `C:\codex sum it up` workspace.

It is intentionally lightweight:

- It does not duplicate the full source of each migrated project.
- It acts as the canonical directory of project repositories.
- It documents which GitHub repo should be used as the future deploy portal for each project.
- It carries the `.io` rollout inventory and the standalone microsites for source-only repos.

The machine-readable inventory lives in `project-index.json`.

## `.io` Rollout Artifacts

- `domain-inventory.json`: selected `.io` candidate per project plus DNS preflight notes
- `render-service-inventory.json`: per-project Render service classification
- `render.yaml`: Render Blueprint for the umbrella microsites
- `microsites/`: standalone static sites for source-only repos

## Future Deploy Flow

Use the project-specific GitHub repository as the source of truth for any future deployment.

- Frontend and static projects: connect the GitHub repo to the chosen frontend host.
- Node backends and proxies: connect the GitHub repo to the chosen Node host.
- Python services: connect the GitHub repo to the chosen Python-capable host.
- Upstream mirrors and tooling repos: treat GitHub as the source mirror unless a separate deploy target is needed later.

## External Account Blockers

The local workspace is ready for the GitHub-side and repo-side parts of the rollout, but these steps still require access to external provider accounts:

- buying the `.io` domains in Namecheap
- adding DNS records in Namecheap
- creating or connecting Render services
- attaching and verifying custom domains in Render

Until those account-side steps are completed, the selected `.io` names in this repo are deployment candidates rather than live production URLs.
