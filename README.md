# home-assistant-config

My Home Assistant config.

## What's here

- `configuration.yaml`, `automations.yaml`, `scripts.yaml`, `scenes.yaml` — core config
- `blueprints/` — automation and script blueprints
- `custom_components/` — HACS-installed integrations
- `www/community/` — HACS-installed frontend resources (Lovelace cards, strategies)
- `secrets.yaml.example` — template for `secrets.yaml`, which is never committed

## What's deliberately excluded

This repo intentionally omits anything that contains credentials, tokens, or
personal data, or that's just regenerated local state:

- `secrets.yaml`, `.storage/`, `.cloud/` — auth tokens, integration credentials, cloud auth
- `*.crt` / `*.key` — TLS cert and private key
- `*.db*`, `*.log*`, `backups/` — recorder/zigbee databases, logs, full backups
- `.cache/`, `deps/`, `tts/`, `__pycache__/` — regenerable local runtime state
- `www/media/` — generated media (e.g. printer timelapses)

See `.gitignore` for the full list.
