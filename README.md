Triple-WEB-DB: High-Availability Tiered Stack

A production-grade, multi-tier infrastructure built on Ubuntu using Docker Compose. This project demonstrates automated load balancing, tiered overflow logic, and centralized database persistence.

🏗 Architecture
The system consists of three distinct layers:
1. Load Balancer (Nginx): Implements a "Tiered Overflow" strategy.
2. Web Tier (Flask): Three identical Python nodes (Alpha, Beta, Gamma).
3. Database Tier (MariaDB): A single source of truth for all web nodes.

🚀 Key Features
- Tiered Overflow: Traffic is locked to the ALPHA node. If ALPHA reaches connection limits (simulating high CPU load), Nginx automatically spills traffic to BETA and GAMMA backups.
- Data Persistence: Database state is stored in a local volume (`db_data/`), ensuring no data loss when containers are restarted.
- Admin Audit Log: A dedicated `/admin` route with auto-refresh (5s) to monitor real-time database ingestion.

🛠 Tech Stack
- OS: Ubuntu (LTS)
- Orchestration: Docker Compose
- Web: Python (Flask), Gunicorn
- DB: MariaDB 10.6
- Proxy: Nginx

