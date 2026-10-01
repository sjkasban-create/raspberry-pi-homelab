# Portainer

Portainer provides a web-based management interface for the Docker environment running on the Raspberry Pi.

## Purpose

Portainer is used to:

- View running and stopped containers
- Inspect container health and status
- Manage Docker resources
- Review container logs
- Monitor deployed services

## Deployment

Portainer Community Edition runs as a Docker container.

The management interfaces are exposed on ports `9000` and `9443`.

Persistent Portainer configuration is stored in the `portainer_data` Docker volume.

The Docker socket is mounted into the container so Portainer can communicate with the local Docker daemon.

## Security

Authentication credentials and Portainer application data are not stored in this repository.
