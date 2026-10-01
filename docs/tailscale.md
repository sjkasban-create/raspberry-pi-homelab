# Tailscale Remote Access

Tailscale provides secure remote access to the Raspberry Pi homelab without exposing management services directly to the public Internet.

## Purpose

Tailscale is used to:

- Remotely access the Raspberry Pi
- Provide encrypted connectivity between authorized devices
- Access homelab services while away from the local network
- Reduce the need for traditional port forwarding

## Architecture

Tailscale creates a private mesh network between authorized devices using WireGuard-based encrypted connections.

Authorized Device
      |
      v
Tailscale Network
      |
      v
Raspberry Pi
      |
      +-- Pi-hole
      +-- Docker Services
      +-- SSH

## DNS Reliability

During testing, DNS configuration was initially dependent on connectivity to the Raspberry Pi through Tailscale.

This created a failure scenario where DNS resolution could stop if the Raspberry Pi or Tailscale connection became unavailable.

The configuration was changed so normal client DNS resolution uses the local router instead of depending on Tailscale DNS.

The router can then use Pi-hole as its primary DNS resolver while maintaining an external fallback resolver.

## Security

Tailscale authentication keys, device credentials, private keys, and other authentication information are not stored in this repository.
