# Issue: HTTP Access Timeout on Windows Client

## Symptoms
- VPN connection established
- Ping to internal server successful
- HTTP access timed out

## Root Cause
Direct HTTP access over VPN was restricted on the client side.

## Solution
Implemented SSH port forwarding to securely access internal services.

Example:
ssh -L 8080:10.10.0.1:80 user@10.10.0.1

