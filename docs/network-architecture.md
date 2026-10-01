# Network Architecture

## Overview

The homelab combines DNS filtering, containerized services, monitoring, and secure remote access on a Raspberry Pi.

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

## DNS Flow

Normal DNS requests follow:

Client -> GL.iNet Router -> Pi-hole -> Upstream DNS

If Pi-hole becomes unavailable:

Client -> GL.iNet Router -> Fallback DNS

This design allows Internet connectivity to continue during a Pi-hole or Raspberry Pi outage.

## Remote Access

Tailscale provides encrypted remote connectivity to the Raspberry Pi without requiring management ports to be directly exposed to the public Internet.

## Monitoring

Uptime Kuma monitors homelab service availability.

Homepage provides a centralized dashboard for accessing services.

Portainer provides Docker container management and monitoring.
