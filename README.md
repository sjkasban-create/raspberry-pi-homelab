# Raspberry Pi Homelab

A self-hosted Raspberry Pi homelab built to explore networking, Linux system administration, containerization, monitoring, and secure remote access.

## Overview

This project uses a Raspberry Pi Zero 2 W as a lightweight homelab server providing network-wide DNS filtering, containerized services, infrastructure monitoring, and remote administration.

## Services

- **Pi-hole** - Network-wide DNS filtering and ad blocking
- **Docker** - Containerized application hosting
- **Portainer** - Docker container management
- **Homepage** - Centralized homelab dashboard
- **Uptime Kuma** - Service availability and uptime monitoring
- **Tailscale** - Secure remote access using a WireGuard-based mesh VPN
- **GL.iNet Router** - Local network routing and DNS configuration

## Network Architecture

Internet
|
GL.iNet Router
|
+-- Client Devices
|
+-- Raspberry Pi Zero 2 W
    |
    +-- Pi-hole
    +-- Tailscale
    +-- Docker
        |
        +-- Homepage
        +-- Uptime Kuma
        +-- Portainer

## Reliability

The network is configured with DNS redundancy so clients can maintain Internet access if the Raspberry Pi or Pi-hole becomes unavailable.

Infrastructure services are monitored using Uptime Kuma.

## Skills Demonstrated

- Linux system administration
- Raspberry Pi
- Docker and containerization
- DNS and DHCP
- TCP/IP networking
- VPN and remote access
- Network monitoring
- YAML configuration
- SSH
- Troubleshooting and system diagnostics

## Project Status

This homelab is actively being developed and documented. Current work includes investigating Raspberry Pi stability, improving monitoring, and implementing additional recovery mechanisms.

## Security

Sensitive information such as passwords, API keys, authentication tokens, webhook URLs, and private configuration values are excluded from this repository.
