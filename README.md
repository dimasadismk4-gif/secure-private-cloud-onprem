# Secure Private Cloud On-Premise

Project ini adalah simulasi **server internal on-premise** yang hanya bisa diakses melalui
jalur aman (VPN WireGuard dan SSH Port Forwarding).

Project ini dibuat untuk menunjukkan pemahaman tentang:
- Networking dasar
- VPN tunnel
- Akses service internal secara aman
- Security awareness (tidak expose service langsung)

---

## Tujuan Project

- Membangun web server internal (Nginx)
- Server **tidak bisa diakses langsung dari jaringan luar**
- Akses hanya diperbolehkan melalui:
  - VPN WireGuard
  - SSH Port Forwarding

---

## Arsitektur Singkat

Client (Windows)
→ VPN WireGuard
→ Server Ubuntu 22.04 (On-Premise)
→ Nginx (Internal Web Server)

---

## Teknologi yang Digunakan

- Ubuntu Server 22.04
- WireGuard VPN
- OpenSSH
- Nginx
- UFW Firewall

---

## Konsep Keamanan

- ICMP (ping) diizinkan untuk testing koneksi
- HTTP **tidak diekspos langsung**
- Akses web dilakukan menggunakan SSH Port Forwarding
- Simulasi server internal seperti di lingkungan perusahaan

---

## Cara Akses Web Server

1. Aktifkan WireGuard tunnel
2. Login SSH ke server:
   ```bash
   ssh -L 8080:10.10.0.1:80 user@10.10.0.1

