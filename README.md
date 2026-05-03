# Homebridge Add-ons for Home Assistant

This repository provides a Home Assistant add-on for running the official
[`homebridge/homebridge`](https://github.com/homebridge/docker-homebridge)
Docker image.

The add-on is intentionally thin:

- It keeps Homebridge configuration, plugin management, logs, and startup
  scripts in the Homebridge UI.
- It preserves the upstream `/homebridge` data model by mapping the Home
  Assistant add-on data directory to `/homebridge`.
- It exposes the standard Homebridge UI instead of patching Homebridge for Home
  Assistant ingress.

## Installation

1. In Home Assistant, open `Settings -> Add-ons -> Add-on Store`.
2. Add `https://github.com/rohanod/ha-addon-homebridge` as an add-on repository.
3. Install `Homebridge`.
4. Start the add-on and open the web UI.

See [homebridge/DOCS.md](homebridge/DOCS.md) for setup details and update
behavior.

## Automation

The scheduled workflow `.github/workflows/bump-homebridge-version.yml` opens
pull requests for Homebridge version bumps.

If the workflow fails with `Input 'token' not supplied`, ensure the workflow is
using `${{ github.token }}` (the built-in `GITHUB_TOKEN`) when calling
`peter-evans/create-pull-request`.

If you see errors like `GitHub Actions is not permitted to create or approve pull requests`,
create a fine-grained PAT with `Contents: Read and write` and
`Pull requests: Read and write` on this repo, and use it instead.
