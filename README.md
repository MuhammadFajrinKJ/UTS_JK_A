# Penetration Test – PT. SecureCorp

Laporan tugas besar mata kuliah **Keamanan Siber / Ethical Hacking**.  
Pengujian dilakukan pada perusahaan fiksi PT. SecureCorp menggunakan metode:

- Passive Reconnaissance (OSINT)
- Active Reconnaissance (Nmap & Wireshark)

🎯 **IP Target:** 10.10.10.50

---

## Passive Recon (OSINT)

Informasi ditemukan:

### Subdomain
- mail.securecorp.com  
- dev.securecorp.com  
- vpn.securecorp.com  
- api.securecorp.com  
- portal.securecorp.com  

### Teknologi
- Apache 2.4.x  
- WordPress CMS  
- Google Analytics  

### Informasi Sensitif
- config.php bocor (Google Dorks)  
- API key bocor (GitHub)  
- error.log terindeks Google  

---

## Active Recon (Nmap)

Perintah yang digunakan:
```
nmap -sS 10.10.10.50
nmap -sU 10.10.10.50
nmap -sV 10.10.10.50
nmap -O 10.10.10.50
```

### Hasil Pemindaian
- Port 22 open (SSH – OpenSSH 8.2)  
- Port 80 open (Apache 2.4.54)  
- Port 443 open (TLS1.3)  
- Port 8080 open (Nginx Proxy)  
- Port 53 open (DNS)  

---

## Kerentanan Ditemukan
- HTTP tanpa enkripsi  
- MySQL terlihat (filtered)  
- Subdomain dev rawan misconfig  
- API key bocor  
- Log error terekspos  

---

## Rekomendasi
- Terapkan HTTPS-only  
- Tutup port MySQL publik  
- Hardening Apache & Nginx  
- Rotasi API key  
- Gunakan VPN + MFA  

---

## Tools
- Nmap  
- Wireshark  
- DNSDumpster  
- crt.sh  
- Subfinder  
- Google Dorks  
- Wappalyzer  
- BuiltWith  

---

**Created for academic purposes – 2025.**
