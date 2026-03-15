# Homebridge Add-ons for Home Assistant

This repository provides a Home Assistant add-on for running the official
[`homebridge/homebridge`](https://github.com/homebridge/docker-homebridge)
Docker image inside the Home Assistant sidebar.

The add-on is intentionally thin:

- It keeps Homebridge configuration, plugin management, logs, and startup
  scripts in the Homebridge UI.
- It preserves the upstream `/homebridge` data model by mapping the Home
  Assistant add-on data directory to `/homebridge`.
- It adds a minimal ingress proxy so Homebridge opens from the Home Assistant
  sidebar while Homebridge itself remains upstream.

## Installation

1. In Home Assistant, open `Settings -> Add-ons -> Add-on Store`.
2. Add `https://github.com/rohanod/ha-addon-homebridge` as an add-on repository.
3. Install `Homebridge`.
4. Start the add-on and open the web UI.

See [homebridge/DOCS.md](homebridge/DOCS.md) for setup details and update
behavior.
