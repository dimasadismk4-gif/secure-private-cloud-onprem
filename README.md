# Secure Private Cloud (Simulasi On-Premise)

## Gambaran Umum
Proyek ini mensimulasikan sistem cloud internal yang aman, dibangun di server on-premise.  
Seluruh layanan terisolasi dari akses publik dan hanya dapat diakses melalui koneksi yang aman.

## Tujuan
- Menerapkan akses layanan internal yang aman  
- Mencegah eksposur langsung layanan ke publik  
- Menggunakan kontrol akses berbasis VPN dan SSH

## Teknologi yang Digunakan
- Ubuntu Server 22.04  
- WireGuard VPN  
- OpenSSH  
- Nginx  
- Firewall UFW

## Arsitektur
- Layanan internal berjalan di alamat IP privat  
- VPN digunakan untuk mengakses jaringan internal  
- SSH digunakan untuk administrasi dan port forwarding  

## Pendekatan Keamanan
- Tidak ada eksposur HTTP publik  
- Akses internal hanya melalui VPN  
- Autentikasi berbasis kunci SSH  
- Port forwarding untuk lingkungan terbatas

## Screenshot

**Konfigurasi VPN**  
<img width="661" height="520" alt="vpn" src="https://github.com/user-attachments/assets/f03c8a0d-d416-4633-9e4d-ae7822b00d8a" />

**SSH Port Forwarding**  
<img width="785" height="487" alt="ssh" src="https://github.com/user-attachments/assets/1770d661-6fe0-48d0-9617-ba5cdef8ee83" />

**LocalHost:8080**  
<img width="1498" height="855" alt="local" src="https://github.com/user-attachments/assets/c84cbcfa-948d-4869-ab67-c7a3c9806ec3" />

**Ping wg0 10.10.0.1**  
<img width="978" height="510" alt="ping" src="https://github.com/user-attachments/assets/1eb49776-2978-41dc-b671-8b201710ba16" />

## Penulis
Dimas Adi Prabowo

