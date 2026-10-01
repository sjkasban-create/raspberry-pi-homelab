# Pi-hole DNS Filtering

Pi-hole provides network-wide DNS filtering for the homelab.

## Purpose

Pi-hole is used to:

- Filter advertising and tracking domains
- Provide network-wide DNS filtering
- Monitor DNS queries
- Experiment with DNS configuration and troubleshooting

## Network Configuration

Pi-hole runs directly on the Raspberry Pi rather than inside a Docker container.

Client devices send DNS requests through the GL.iNet router, which is configured to use Pi-hole as its primary DNS resolver.

A secondary external DNS resolver provides redundancy if the Raspberry Pi or Pi-hole becomes unavailable.

## DNS Architecture

Client Devices
      |
      v
GL.iNet Router
      |
      +---- Primary DNS ----> Pi-hole
      |
      +---- Fallback DNS ---> External DNS Resolver

## Reliability

DNS redundancy was implemented after testing failure scenarios involving the Raspberry Pi and remote-access services.

This allows client devices to maintain DNS resolution if the Raspberry Pi becomes unavailable. Pi-hole filtering is bypassed while the fallback DNS resolver is being used.

## Security

Pi-hole passwords, authentication information, DNS query logs, and other sensitive runtime data are not stored in this repository.
