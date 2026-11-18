# Homelab GitOps Docker Configuration

This repository manages a 13-container homelab architecture orchestrated via **Dockge** and **git-sync**.

## Directory Structure
- `01-infrastructure/`: Dockge UI, git-sync auto-poller, and Nginx Proxy Manager.
- `02-automation/`: Home Assistant and Mosquitto MQTT broker.
- `03-media-photos/`: Jellyfin media server and Immich photo backup suite (server, ML, Redis, Postgres).
- `04-cctv-backup/`: Frigate NVR for ONVIF cameras and automated Rclone backup loop.
- `05-cloud-finance/`: Nextcloud file storage, Paperless-ngx document OCR, and Actual Budget financial planner.

## Quick Start
1. Copy `.env.sample` to `.env` on your host machine (and inside stack folders as needed in Dockge) and fill in your secrets.
2. Bootstrap `01-infrastructure` manually on the host (`docker compose up -d`).
3. Open Dockge at `http://<server-ip>:5001` to deploy the synced stacks (`02` through `05`).
