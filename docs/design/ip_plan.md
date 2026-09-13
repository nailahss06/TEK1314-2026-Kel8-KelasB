# IP Plan — Kelompok 8

## Skenario
Proyek PBL Keamanan Siber (TEK1314) — simulasi serangan terhadap server target di jaringan lokal, dengan node monitoring (Security Onion) untuk memantau seluruh trafik pada segmen jaringan kelompok.

## Subnet
- **Network:** 192.168.8.0/24
- **Subnet Mask:** 255.255.255.0

## Tabel IP Address

| Hostname                     | IP Address     | OS Direncanakan     | Keterangan                                                                 |
|-------------------------------|----------------|----------------------|------------------------------------------------------------------------------|
| Target Server (Korban)        | 192.168.8.5    | Ubuntu Server        | Server target yang akan diserang (celah keamanan menunggu masukan Red Team) |
| Attacker Node                 | 192.168.8.100  | Kali Linux           | Node penyerang, menjalankan tools/script analisis dan eksploitasi           |
| Monitoring Node               | 192.168.8.200  | Security Onion (VM)  | Berjalan di VM terpisah; NIC diset mode promiscuous untuk port mirroring/SPAN dari switch agar dapat memantau seluruh trafik segmen |


