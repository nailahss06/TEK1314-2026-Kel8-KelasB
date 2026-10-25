TABEL DEKLARASI TECH STACK

|Komponen|Teknologi pada Proyek IoT Asli|Direplikasi sebagai (Target Node)|
|-|-|-|
|Sistem Operasi backend|Cloud Platform (PaaS Render \& Supabase Cloud)|Ubuntu Server 22.04 LTS (CyberOps LabVM 192.168.10.10)|
|Database|Supabase (Cloud Database PostgreSQL + Realtime|MySQL Server 8.0 / PostgreSQL Lokal (Port 3306/tcp, DB sassy\_db)|
|Protokol komunikasi sensor|HTTPS / REST API (Port 443 via Wi-Fi) \& MQTT fallback|Eclipse Mosquitto v2.0 (Port 1883/tcp) \& REST API (Port 5000/tcp)|
|Dashboard/monitoring|Next.js Dashboard (Vercel) + FastAPI (Render|Nginx Web Server (Port 80/tcp) + Python Flask/FastAPI Backend (Port 5000/tcp)|





