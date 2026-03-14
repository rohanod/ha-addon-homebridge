# Homebridge

Run the official Homebridge Docker image as a Home Assistant add-on.

This add-on keeps the upstream Homebridge workflow intact:

- access the Homebridge UI on port `8581`
- manage plugins and `config.json` in the Homebridge UI
- persist Homebridge data in the add-on data directory, mounted at
  `/homebridge`

See [DOCS.md](DOCS.md) for setup and update guidance.
