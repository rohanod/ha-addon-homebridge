# Homebridge Add-on

## About

This add-on runs the official
[`homebridge/homebridge`](https://github.com/homebridge/docker-homebridge)
container inside Home Assistant.

The add-on is designed to stay close to upstream behavior:

- Homebridge runs with host networking, which is required for HomeKit discovery.
- The Home Assistant add-on data directory is mounted at `/homebridge`, which
  matches the official Homebridge Docker image.
- The add-on tracks the upstream multi-architecture `homebridge/homebridge`
  image for `amd64`, `aarch64`, and `armv7`.
- The Homebridge UI remains the primary place to manage configuration, plugins,
  logs, restarts, and startup scripts.

## First Start

1. Install the add-on.
2. Start the add-on.
3. Open the web UI from Home Assistant, or browse to
   `http://<home-assistant-host>:8581`.
4. Sign in with the default Homebridge UI credentials:
   - username: `admin`
   - password: `admin`
5. Change the Homebridge UI credentials after your first login.

## Notes

- This add-on does not use Home Assistant ingress in v1. The Homebridge UI is
  exposed directly on port `8581`.
- Host networking is enabled because the official Homebridge Docker image
  requires it for HomeKit discovery.
- Homebridge plugins, `config.json`, `package.json`, `node_modules`, and
  `startup.sh` persist in the add-on data directory because that directory is
  mounted at `/homebridge`.

## Updates

- Update the add-on to pull a newer Homebridge container image.
- This add-on tracks the upstream `latest` Homebridge image tag.
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
