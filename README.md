# MiniCloud – Local Cloud Platform Simulation

This project simulates a minimal cloud-like environment similar to AWS, Azure, or OCI, using Docker containers.  
It includes a lightweight Kubernetes distribution, monitoring, and a custom dashboard for container visibility.

---

## 📦 Components

### 1. **K3s (Lightweight Kubernetes)**
- Provides the core orchestration layer for simulating cloud workloads.
- **Port:** `6443`

### 2. **Prometheus**
- Collects metrics from K3s and other services.
- **Port:** `9090`

### 3. **Grafana**
- Visualizes metrics and dashboards from Prometheus.
- **Port:** `3000`

### 4. **Flask Dashboard**
- Custom lightweight web interface that shows the status of running Docker containers.
- Displays container health with **red/yellow/green indicators**.
- **Port:** `5000`

---

## 🚀 Usage

1. Clone this repository:
   ```bash
   git clone https://github.com/yourusername/minicloud.git
   cd minicloud
Start the stack:
  - docker-compose up -d
  - Access the services:

Flask Dashboard: http://localhost:5000

Prometheus: http://localhost:9090

Grafana: http://localhost:3000

K3s API: Accessible internally at localhost:6443

🖼 Architecture

🔧 Requirements
Docker (>= 20.x)

Docker Compose (>= 1.29)

📝 Notes
- Cilium is optional for CNI and advanced networking. It may fail to run unless the host supports the required kernel settings (e.g., /proc/sys/net/ipv6 entries). Feel free to comment it out in docker-compose.yml if you don't need to.
- 
- The Flask Dashboard container automatically installs Flask at build time via the requirements.txt file.

✅ Roadmap
Add object storage simulation (MinIO)

Add message queue (NATS or RabbitMQ)

Add an authentication service
