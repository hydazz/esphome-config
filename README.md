# esphome-config

Some ESPHome configurations, based on [bjw-s-labs/esphome-config](https://github.com/bjw-s-labs/esphome-config).

Each root-level YAML file is a device. Subdirectories contain shared packages.

Run `mise install` and `mise run deps`. Mise selects Python, activates the project
environment and installs Lefthook. ESPHome is pinned in `pyproject.toml`;
`uv.lock` records its Python dependencies.

Provide a local, ignored `secrets.yaml` with the keys in
[.github/secrets.example.yaml](.github/secrets.example.yaml). The example contains
dummy values for CI. The cluster gets its real secrets from External Secrets.

```sh
mise run lint
mise run lint water-heater.yaml
mise run compile water-heater.yaml
mise run deploy water-heater.yaml water-heater.iot
mise run logs water-heater.yaml water-heater.iot
mise run format
```
