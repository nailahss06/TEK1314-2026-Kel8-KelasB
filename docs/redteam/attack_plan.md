Attack Plan — Red Team (Kelompok 8)

A. Ruang Lingkup
Pengujian difokuskan pada satu Target Node: VM-Server (192.168.10.10) di mana terdapat service database (MySQL) dan dashboard dengan port yang berbeda.

B. Skenario Serangan
1. Skenario 1 — Reconnaissance
Tool: Nmap (nmap -sV -p-)
Target: 192.168.10.10
Tujuan: Memetakan seluruh port terbuka dan versi service yang berjalan di Target Node, sebagai dasar identifikasi celah untuk skenario eksploitasi berikutnya.
Alasan pemilihan: Nmap adalah tool standar untuk network reconnaissance, mampu memindai seluruh 65535 port TCP beserta versinya. Tahap ini merepresentasikan langkah awal yang umum dilakukan penyerang sebelum menentukan vektor serangan.

2. Skenario 2 — Exploitation / Akses
Tools: Hydra + wordlist "rockyou.txt"
Target: 192.168.10.10:2222 (SSH)
Tujuan: Brute-force SSH untuk menguji apakah password authentication masih aktif atau sudah dibatasi hanya key-based auth.
Alasan pemilihan: rockyou.txt berisi 14+ juta password nyata dari kebocoran data RockYou (2009), merepresentasikan pola password lemah yang umum dipakai pengguna — lebih relevan dibanding wordlist acak buatan. Hydra dipakai karena mendukung protokol SSH secara native dan jadi tool brute-force standar di pentest.

3. Skenario 3 — Web/API/Protokol IoT
Tool: mosquitto_sub / mosquitto_pub
Target: 192.168.10.10:1883 (MQTT Broker)
Tujuan: Menguji apakah broker MQTT menerima koneksi anonymous atau kredensial default/umum.
Alasan pemilihan: mosquitto_sub/pub adalah client resmi ekosistem MQTT, protokol yang sama persis dipakai SASSY untuk transmisi data sensor. Pengujian ini merepresentasikan celah autentikasi broker yang umum terjadi pada implementasi IoT yang kurang hardening.
