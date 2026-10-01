# Uptime Kuma

Uptime Kuma provides service availability and uptime monitoring for the homelab.

## Deployment

The service runs as a Docker container and is exposed on port `3001`.

Persistent application data is stored using a Docker volume mounted at `/app/data`.

## Monitored Services

The monitoring environment is designed to track services including:

- Pi-hole
- Homepage
- Portainer
- Raspberry Pi host availability

## Reliability

The container uses the `unless-stopped` restart policy so Docker automatically attempts to restart the service following a system reboot or unexpected container shutdown.
