# Codex Sum It Up Workspace Mirror

This repository is the umbrella GitHub index for the `C:\codex sum it up` workspace.

It is intentionally lightweight:

- It does not duplicate the full source of each migrated project.
- It acts as the canonical directory of project repositories.
- It documents which GitHub repo should be used as the future deploy portal for each project.

The machine-readable inventory lives in `project-index.json`.

## Future Deploy Flow

Use the project-specific GitHub repository as the source of truth for any future deployment.

- Frontend and static projects: connect the GitHub repo to the chosen frontend host.
- Node backends and proxies: connect the GitHub repo to the chosen Node host.
- Python services: connect the GitHub repo to the chosen Python-capable host.
- Upstream mirrors and tooling repos: treat GitHub as the source mirror unless a separate deploy target is needed later.
