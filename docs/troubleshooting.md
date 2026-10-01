# Troubleshooting and Reliability

This homelab has also been used to practice diagnosing real networking, Linux, and container reliability problems.

## DNS Failure

### Problem

Client devices temporarily lost DNS resolution when the Raspberry Pi or Tailscale connection became unavailable.

Internet connectivity was still present, but domain names could not be resolved.

### Investigation

Testing showed that direct IP connectivity still worked while DNS queries failed.

This helped isolate the problem to DNS rather than the Internet connection itself.

### Solution

DNS was redesigned so client devices use the GL.iNet router for DNS.

The router uses:

- Pi-hole as the primary DNS resolver
- An external DNS resolver as a fallback

This allows Internet access to continue if Pi-hole becomes unavailable.

## Raspberry Pi Stability

The Raspberry Pi has occasionally become unreachable and required a restart.

Troubleshooting has included monitoring:

- Memory utilization
- Swap utilization
- CPU load
- System logs
- Network connectivity
- Docker container health
- Power and thermal conditions

The root cause is still under investigation.

## Docker Recovery

Following unexpected system interruptions, some Docker containers failed to restart correctly.

Troubleshooting included:

- Inspecting container status
- Reviewing Docker and containerd logs
- Restarting Docker services
- Examining container restart policies
- Recovering individual containers

## Lessons Learned

This project demonstrates the importance of:

- Designing services with failure scenarios in mind
- Maintaining DNS redundancy
- Monitoring system resources
- Using persistent logs for troubleshooting
- Protecting configuration secrets
- Documenting infrastructure changes
