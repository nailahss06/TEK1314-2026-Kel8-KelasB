1. Kategori A: Access & Authentication (Status: 100% Selesai)
* A1 - Nonaktifkan Root Login: PermitRootLogin no di /etc/ssh/sshd_config. Login root ditolak sistem. (Status: Selesai)
* A2 - SSH Key-Based Auth: Wajib kunci RSA 2048-bit, password auth dimatikan total (PasswordAuthentication no). (Status: Selesai)
* A3 - Ubah Port SSH: Port standar 22 dipindah ke port kustom 2222. Port 22 connection refused. (Status: Selesai)
* A4 - Anti Brute-Force Fail2ban: Proteksi jail sshd aktif di port 2222 (maxretry = 3, bantime = 600s). (Status: Selesai)[

2. Kategori B: Service & Attack Surface (Status: 100% Selesai)
* B1 - Firewall UFW Ketat: Kebijakan default deny incoming, hanya whitelist port esensial (2222, 1883, 3306, 80, 5000). (Status: Selesai)
* B2 - Matikan Service Non-Esensial: Menonaktifkan service discovery & printer (cups, avahi-daemon, rpcbind). (Status: Selesai)
* B3 - OS & Paket Patching: Repositori dan security patch mutakhir (apt update && apt upgrade). (Status: Selesai)
* B4 - Pengamanan Kredensial MySQL: Hapus anonymous user, cabut akses remote root database. (Status: Selesai)

3. Kategori C: Data & Application (Status: 100% Selesai)
* C1 - Isolasi Kredensial: Kredensial DB/MQTT dipisah ke file .env dengan hak akses terbatas (chmod 600). (Status: Selesai)
* C2 - Wajib Autentikasi MQTT: Mosquitto menolak akses anonim (allow_anonymous false), wajib user sassy_client. (Status: Selesai)
* C3 - Least Privilege User DB: User aplikasi sassy_app dibatasi hanya CRUD pada database sassy_db. (Status: Selesai)
* C4 - Audit Trail & Logging: Logging aktif pada auth.log, mosquitto.log, dan fail2ban.log. (Status: Selesai)