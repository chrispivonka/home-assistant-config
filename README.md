# home-assistant-config

My Home Assistant config.

## What's here

- `configuration.yaml`, `automations.yaml`, `scripts.yaml`, `scenes.yaml` — core config
- `blueprints/` — automation and script blueprints
- `custom_components/` — HACS-installed integrations
- `www/community/` — HACS-installed frontend resources (Lovelace cards, strategies)
- `secrets.yaml.example` — template for `secrets.yaml`, which is never committed
- `docker-compose.yml` — the stack this runs on (Home Assistant, Matter server, Z-Wave JS UI)

Dashboards aren't included as static files — they're auto-generated
[mushroom-strategy](https://github.com/AalianKhan/mushroom-strategy) /
[bonbon-strategy](https://github.com/elchininet/bonbon-strategy) layouts with
no manual card config to capture; reinstalling the frontend resources above
regenerates them. A Caddy reverse proxy sits in front of this on the host
(not included here — it's shared with unrelated services outside this repo).

## What's deliberately excluded

This repo intentionally omits anything that contains credentials, tokens, or
personal data, or that's just regenerated local state:

- `secrets.yaml`, `.storage/`, `.cloud/` — auth tokens, integration credentials, cloud auth
- `*.crt` / `*.key` — TLS cert and private key
- `*.db*`, `*.log*`, `backups/` — recorder/zigbee databases, logs, full backups
- `.cache/`, `deps/`, `tts/`, `__pycache__/` — regenerable local runtime state
- `www/media/` — generated media (e.g. printer timelapses)

Also excluded, but living outside this config dir entirely so not gitignored
here: `zwave-data/` and `matter-data/` (Z-Wave network security keys, Matter
fabric credentials) on the host.

See `.gitignore` for the full list.
