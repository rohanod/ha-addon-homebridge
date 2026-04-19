# Homebridge Add-on

## About

This add-on runs the official
[`homebridge/homebridge`](https://github.com/homebridge/docker-homebridge)
container inside Home Assistant without patching Homebridge itself for ingress.

The add-on is designed to stay close to upstream behavior:

- Homebridge runs with host networking, which is required for HomeKit discovery.
- The Home Assistant add-on data directory is mounted at `/homebridge`, which
  matches the official Homebridge Docker image.
- The add-on is pinned to a specific upstream multi-architecture
  `homebridge/homebridge` tag for `amd64`, `aarch64`, and `armv7`.
- The Homebridge UI remains the primary place to manage configuration, plugins,
  logs, restarts, and startup scripts.

## First Start

1. Install the add-on.
2. Start the add-on.
3. Open the Homebridge Web UI from the add-on page, or browse to
   `http://<home-assistant-host>:8581`.
4. Sign in with the default Homebridge UI credentials:
   - username: `admin`
   - password: `admin`
5. Change the Homebridge UI credentials after your first login.

## Notes

- Host networking is enabled because the official Homebridge Docker image
  requires it for HomeKit discovery.
- Homebridge plugins, `config.json`, `package.json`, `node_modules`, and
  `startup.sh` persist in the add-on data directory because that directory is
  mounted at `/homebridge`.
- The Homebridge UI is served on port `8581`, matching upstream.
- If you need remote access through the same public entrypoint as Home
  Assistant, put Homebridge behind your own reverse proxy rather than Home
  Assistant ingress.

## Updates

- Update this repository's add-on version to a newer upstream Homebridge image
  tag, then update the add-on in Home Assistant.
- This add-on uses a manually pinned upstream Homebridge image tag.
- Use the Homebridge UI for plugin installation and plugin updates.
- Do not rely on in-container updates of Homebridge core, Homebridge UI, or the
  Node.js runtime. Those are overwritten when the container image is updated.

## Support

- Homebridge Docker docs:
  <https://github.com/homebridge/docker-homebridge/blob/latest/README.md>
- Homebridge Docker setup guide:
  <https://github.com/homebridge/homebridge/wiki/Install-Homebridge-on-Docker>
- Homebridge UI docs:
  <https://github.com/homebridge/homebridge-config-ui-x/blob/latest/README.md>
