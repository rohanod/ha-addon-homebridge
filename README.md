# Homebridge Add-ons for Home Assistant

This repository provides a Home Assistant add-on for running the official
[`homebridge/homebridge`](https://github.com/homebridge/docker-homebridge)
Docker image.

The add-on is intentionally thin:

- It keeps Homebridge configuration, plugin management, logs, and startup
  scripts in the Homebridge UI.
- It preserves the upstream `/homebridge` data model by mapping the Home
  Assistant add-on data directory to `/homebridge`.
- It exposes the Homebridge UI directly on port `8581` instead of depending on
  Home Assistant ingress.

## Installation

1. In Home Assistant, open `Settings -> Add-ons -> Add-on Store`.
2. Add `https://github.com/rohanod/ha-addon-homebridge` as an add-on repository.
3. Install `Homebridge`.
4. Start the add-on and open the web UI.

See [homebridge/DOCS.md](homebridge/DOCS.md) for setup details and update
behavior.
