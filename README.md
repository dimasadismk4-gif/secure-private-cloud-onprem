# Secure Internal Private Cloud (On-Premise Simulation)

Project ini mensimulasikan **infrastruktur server internal perusahaan**
yang **tidak mengekspos layanan web ke publik**, dan hanya dapat diakses
melalui jalur aman (VPN dan SSH Port Forwarding).

Project ini menekankan:
- Pemisahan jaringan
- Kontrol akses service
- Prinsip security-first
- Cara kerja infrastruktur internal di dunia kerja

---

## Problem Statement

Banyak server internal perusahaan:
- Tidak boleh diakses langsung via IP
- Tidak membuka port HTTP ke publik
- Hanya bisa diakses oleh IT / Admin tertentu

Project ini mensimulasikan kondisi tersebut.

---

## Objectives

- Membangun web server internal berbasis Nginx
- Menempatkan server dalam jaringan private
- Mengamankan akses menggunakan:
  - WireGuard VPN
  - SSH Port Forwarding
- Membuktikan bahwa web hanya bisa diakses
  melalui jalur yang terkontrol

---

## Infrastructure Overview

Client (Windows)
→ WireGuard VPN (Encrypted Tunnel)
→ Ubuntu Server 22.04 (On-Premise)
→ Nginx (Internal Web Service)

---

## Network Design

- VPN Network: `10.10.0.0/24`
- Server IP: `10.10.0.1`
- Client VPN IP: `10.10.0.2`
- Public HTTP access: **DISABLED**

---

## Security Design

| Component | Policy |
|---|---|
| WireGuard | Encrypted access |
| SSH | Authenticated admin access |
| HTTP (80) | Not exposed |
| Firewall | Default deny |
| ICMP | Allowed for testing only |

---

## Access Flow (How It Works)

1. Client connects to WireGuard VPN
2. Client can **ping server** (network verified)
3. Client **cannot access HTTP directly**
4. Client establishes SSH session with port forwarding
5. Local port is mapped to internal web service
6. Web becomes accessible **only while SSH is active**

---

## Accessing Internal Web Service

### Step 1 – Connect VPN
```bash
ping 10.10.0.1

### Step 2 – Secure Access via SSH Tunnel
```bash
ssh -L 8080:10.10.0.1:80 dimas@10.10.0.1

### Step 3 – Open Web
```bash
http://localhost:8080

Closing SSH session immediately cuts web access.

## AUTHOR

Dimas Adi Prabowo
