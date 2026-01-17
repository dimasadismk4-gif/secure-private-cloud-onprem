# Secure Private Cloud (On-Premise Simulation)

## Overview
This project simulates a secure internal cloud system built on an on-premise server.
All services are isolated from public access and can only be reached through secure
connections.

## Objectives
- Implement secure internal service access
- Prevent direct public exposure of services
- Apply VPN and SSH-based access control

## Technology Stack
- Ubuntu Server 22.04
- WireGuard VPN
- OpenSSH
- Nginx
- UFW Firewall

## Architecture
- Internal services run on private IP addresses
- VPN tunnel used for internal network access
- SSH used for administration and port forwarding

## Security Approach
- No public HTTP exposure
- VPN-only internal access
- SSH key-based authentication
- Port forwarding for restricted environments

## Author
Dimas Adi Prabowo

