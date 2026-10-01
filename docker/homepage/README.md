# Homepage

Homepage provides a centralized dashboard for accessing and monitoring services running in the Raspberry Pi homelab.

## Services Displayed

The dashboard provides links to homelab infrastructure including:

- Pi-hole
- Portainer
- Uptime Kuma
- Router management
- Other self-hosted services

## Configuration

Homepage is configured using YAML files:

- `services.yaml` - Defines homelab services displayed on the dashboard
- `widgets.yaml` - Configures dashboard widgets
- `bookmarks.yaml` - Stores dashboard bookmarks
- `settings.yaml` - Controls Homepage settings
- `docker.yaml` - Configures Docker integration

## Security

API keys and other credentials are not stored in this repository.

Placeholder values are used where credentials would normally be required.

## Deployment

Homepage runs as a Docker container and is exposed on port `3000`.

The Docker socket is mounted read-only to allow Homepage to retrieve container status information.
