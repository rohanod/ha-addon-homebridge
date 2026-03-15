# Homebridge

Run Homebridge as a Home Assistant add-on with sidebar access through ingress.

This add-on keeps the upstream Homebridge workflow intact while adding a small
ingress proxy layer for Home Assistant:

- open Homebridge from the Home Assistant sidebar
- manage plugins and `config.json` in the Homebridge UI
- persist Homebridge data in the add-on data directory, mounted at
  `/homebridge`

See [DOCS.md](DOCS.md) for setup and update guidance.
