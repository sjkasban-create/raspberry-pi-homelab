# Raspberry Pi Homelab

A self-hosted Raspberry Pi homelab built to explore networking, Linux system administration, containerization, infrastructure monitoring, DNS, and secure remote access.

## Overview

This project uses a Raspberry Pi Zero 2 W as a lightweight homelab server for network-wide DNS filtering, containerized services, infrastructure monitoring, and remote administration.

The project also serves as a hands-on environment for troubleshooting networking and system reliability problems.

## Architecture

                         Internet
                            |
                            v
                     GL.iNet Router
                            |
             +--------------+--------------+
             |                             |
             v                             v
       Client Devices              Raspberry Pi Zero 2 W
                                          |
                    +---------------------+---------------------+
                    |                     |                     |
                    v                     v                     v
                 Pi-hole              Tailscale              Docker
                                                                |
                                              +-----------------+----------------+
                                              |                 |                |
                                              v                 v                v
                                           Homepage        Uptime Kuma       Portainer

## Services

| Service | Purpose |
| --- | --- |
| Pi-hole | Network-wide DNS filtering |
| Tailscale | Secure remote access |
| Docker | Containerized service hosting |
| Homepage | Centralized homelab dashboard |
| Uptime Kuma | Service availability monitoring |
| Portainer | Docker management |
| GL.iNet Router | Routing and DNS configuration |

## DNS Reliability

Client devices use the GL.iNet router for DNS resolution.

The router is configured to use Pi-hole as the primary DNS resolver while maintaining an external fallback resolver.

Normal operation:

Client -> Router -> Pi-hole -> Upstream DNS

Failure scenario:

Client -> Router -> Fallback DNS

This allows Internet connectivity to continue if the Raspberry Pi or Pi-hole becomes unavailable.

## Repository Structure

    raspberry-pi-homelab/
    |
    +-- docker/
    |   +-- homepage/
    |   +-- uptime-kuma/
    |   +-- portainer/
    |
    +-- docs/
    |   +-- network-architecture.md
    |   +-- pihole.md
    |   +-- tailscale.md
    |   +-- troubleshooting.md
    |
    +-- README.md
    +-- .gitignore

## Documentation

- [Network Architecture](docs/network-architecture.md)
- [Pi-hole DNS Filtering](docs/pihole.md)
- [Tailscale Remote Access](docs/tailscale.md)
- [Troubleshooting and Reliability](docs/troubleshooting.md)
- [Homepage](docker/homepage/README.md)
- [Uptime Kuma](docker/uptime-kuma/README.md)
- [Portainer](docker/portainer/README.md)

## Skills Demonstrated

- Linux system administration
- Raspberry Pi administration
- Docker and containerization
- DNS configuration and troubleshooting
- TCP/IP networking
- VPN and remote access
- Network monitoring
- Infrastructure troubleshooting
- YAML configuration
- Git and GitHub
- SSH
- Service availability and reliability

## Troubleshooting

The homelab has been used to investigate real infrastructure problems including:

- DNS resolution failures
- Raspberry Pi availability issues
- Memory and swap utilization
- Docker container failures
- Container restart behavior
- Tailscale connectivity
- Network failover

Troubleshooting procedures and lessons learned are documented in [Troubleshooting and Reliability](docs/troubleshooting.md).

## Security

Sensitive information is intentionally excluded from this repository.

The repository does not contain:

- Passwords
- Private SSH keys
- Tailscale authentication keys
- API keys
- Webhook URLs
- Pi-hole query logs
- Application databases

Placeholder values are used where credentials would normally be required.

## Project Status

This homelab is actively maintained and expanded as a hands-on environment for networking, cybersecurity, Linux administration, and infrastructure experimentation.1~# Raspberry Pi Homelab

A self-hosted Raspberry Pi homelab built to explore networking, Linux system administration, containerization, infrastructure monitoring, DNS, and secure remote access.

## Overview

This project uses a Raspberry Pi Zero 2 W as a lightweight homelab server for network-wide DNS filtering, containerized services, infrastructure monitoring, and remote administration.

The project also serves as a hands-on environment for troubleshooting networking and system reliability problems.

## Architecture

                         Internet
                            |
                            v
                     GL.iNet Router
                            |
             +--------------+--------------+
             |                             |
             v                             v
       Client Devices              Raspberry Pi Zero 2 W
                                          |
                    +---------------------+---------------------+
                    |                     |                     |
                    v                     v                     v
                 Pi-hole              Tailscale              Docker
                                                                |
                                              +-----------------+----------------+
                                              |                 |                |
                                              v                 v                v
                                           Homepage        Uptime Kuma       Portainer

## Services

| Service | Purpose |
| --- | --- |
| Pi-hole | Network-wide DNS filtering |
| Tailscale | Secure remote access |
| Docker | Containerized service hosting |
| Homepage | Centralized homelab dashboard |
| Uptime Kuma | Service availability monitoring |
| Portainer | Docker management |
| GL.iNet Router | Routing and DNS configuration |

## DNS Reliability

Client devices use the GL.iNet router for DNS resolution.

The router is configured to use Pi-hole as the primary DNS resolver while maintaining an external fallback resolver.

Normal operation:

Client -> Router -> Pi-hole -> Upstream DNS

Failure scenario:

Client -> Router -> Fallback DNS

This allows Internet connectivity to continue if the Raspberry Pi or Pi-hole becomes unavailable.

## Repository Structure

    raspberry-pi-homelab/
    |
    +-- docker/
    |   +-- homepage/
    |   +-- uptime-kuma/
    |   +-- portainer/
    |
    +-- docs/
    |   +-- network-architecture.md
    |   +-- pihole.md
    |   +-- tailscale.md
    |   +-- troubleshooting.md
    |
    +-- README.md
    +-- .gitignore

## Documentation

- [Network Architecture](docs/network-architecture.md)
- [Pi-hole DNS Filtering](docs/pihole.md)
- [Tailscale Remote Access](docs/tailscale.md)
- [Troubleshooting and Reliability](docs/troubleshooting.md)
- [Homepage](docker/homepage/README.md)
- [Uptime Kuma](docker/uptime-kuma/README.md)
- [Portainer](docker/portainer/README.md)

## Skills Demonstrated

- Linux system administration
- Raspberry Pi administration
- Docker and containerization
- DNS configuration and troubleshooting
- TCP/IP networking
- VPN and remote access
- Network monitoring
- Infrastructure troubleshooting
- YAML configuration
- Git and GitHub
- SSH
- Service availability and reliability

## Troubleshooting

The homelab has been used to investigate real infrastructure problems including:

- DNS resolution failures
- Raspberry Pi availability issues
- Memory and swap utilization
- Docker container failures
- Container restart behavior
- Tailscale connectivity
- Network failover

Troubleshooting procedures and lessons learned are documented in [Troubleshooting and Reliability](docs/troubleshooting.md).

## Security

Sensitive information is intentionally excluded from this repository.

The repository does not contain:

- Passwords
- Private SSH keys
- Tailscale authentication keys
- API keys
- Webhook URLs
- Pi-hole query logs
- Application databases

Placeholder values are used where credentials would normally be required.

## Project Status

This homelab is actively maintained and expanded as a hands-on environment for networking, cybersecurity, Linux administration, and infrastructure experimentation.
