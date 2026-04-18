# ⚡ Daily Task Adder — DevOps College Project

> A full-stack task management app built with a complete DevOps pipeline including CI/CD, Docker, Kubernetes, Terraform, and Monitoring.

![GitHub Actions](https://img.shields.io/badge/CI%2FCD-GitHub_Actions-2088FF?logo=github-actions)
![Docker](https://img.shields.io/badge/Docker-Containerized-2496ED?logo=docker)
![Kubernetes](https://img.shields.io/badge/Kubernetes-Orchestrated-326CE5?logo=kubernetes)
![Terraform](https://img.shields.io/badge/IaC-Terraform-7B42BC?logo=terraform)
![Prometheus](https://img.shields.io/badge/Monitoring-Prometheus-E6522C?logo=prometheus)

---

## 🏗️ Tech Stack

| Layer | Technology |
|---|---|
| Frontend | React.js + CSS Modules |
| Backend | Node.js + Express.js |
| Database | MongoDB |
| Containerization | Docker + Docker Compose |
| Orchestration | Kubernetes |
| CI/CD | GitHub Actions |
| IaC | Terraform |
| Monitoring | Prometheus + Grafana |

---

## 📁 Project Structure

```
daily-task-adder/
├── frontend/                  → React.js app
│   ├── src/
│   │   ├── components/        → Header, TaskForm, TaskList
│   │   ├── App.js
│   │   └── index.js
│   ├── Dockerfile
│   └── nginx.conf
├── backend/                   → Node.js Express API
│   ├── models/Task.js         → Mongoose schema
│   ├── routes/tasks.js        → REST API routes
│   ├── tests/                 → Jest unit tests
│   ├── app.js
│   └── Dockerfile
├── k8s/                       → Kubernetes manifests
│   ├── backend-deployment.yml
│   ├── frontend-deployment.yml
│   └── mongo-deployment.yml
├── terraform/                 → Infrastructure as Code
│   └── main.tf
├── monitoring/                → Prometheus + Grafana
│   ├── prometheus.yml
│   └── grafana/
├── .github/workflows/         → GitHub Actions CI/CD
│   └── cicd.yml
├── docker-compose.yml         → Local dev environment
└── README.md
```

---

## 🚀 Quick Start (Local Dev)

### Prerequisites
- Docker Desktop installed
- Node.js 18+
- Git

### Step 1: Clone the repo
```bash
git clone https://github.com/Prithvi2400/daily-task-adder.git
cd daily-task-adder
```

### Step 2: Run with Docker Compose
```bash
docker-compose up --build
```

### Step 3: Access the app
| Service | URL |
|---|---|
| Frontend | http://localhost:3000 |
| Backend API | http://localhost:5000 |
| Prometheus | http://localhost:9090 |
| Grafana | http://localhost:3001 |

> Grafana login: `admin` / `admin123`

---

## 🐳 Docker Commands

```bash
# Build images
docker build -t prithvi2400/daily-task-backend ./backend
docker build -t prithvi2400/daily-task-frontend ./frontend

# Push to Docker Hub
docker push prithvi2400/daily-task-backend
docker push prithvi2400/daily-task-frontend

# Run all services
docker-compose up -d

# Stop all services
docker-compose down
```

---

## ☸️ Kubernetes Deployment

```bash
# Apply all manifests
kubectl apply -f k8s/

# Check pods status
kubectl get pods

# Check services
kubectl get services

# View logs
kubectl logs deployment/backend-deployment
```

---

## 🌍 Terraform Commands

```bash
cd terraform

# Initialize
terraform init

# Preview changes
terraform plan

# Apply infrastructure
terraform apply -auto-approve

# Destroy infrastructure
terraform destroy -auto-approve
```

---

## 🔄 CI/CD Pipeline

The GitHub Actions pipeline runs automatically on every push to `main`:

```
Push to main
    ↓
🧪 Test Backend (Jest)
🧪 Test Frontend (React)
    ↓
🐳 Build Docker Images
🐳 Push to Docker Hub
    ↓
☸️ Deploy to Kubernetes
    ↓
✅ Pipeline Complete
```

### Setting up GitHub Secrets
Go to your repo → Settings → Secrets and add:

| Secret | Value |
|---|---|
| `DOCKER_USERNAME` | `Prithvi2400` |
| `DOCKER_PASSWORD` | Your Docker Hub password |
| `KUBECONFIG` | Your kubectl config content |

---

## 📊 Monitoring

### Prometheus
- Scrapes metrics from backend every 10 seconds
- Access at: http://localhost:9090

### Grafana
- Pre-configured with Prometheus datasource
- Access at: http://localhost:3001
- Login: `admin` / `admin123`
- Metrics tracked:
  - HTTP request count
  - Response latency
  - CPU & Memory usage

---

## 🔌 API Endpoints

| Method | Endpoint | Description |
|---|---|---|
| GET | `/api/tasks?date=YYYY-MM-DD` | Get tasks for a date |
| POST | `/api/tasks` | Create new task |
| PATCH | `/api/tasks/:id` | Toggle task complete |
| DELETE | `/api/tasks/:id` | Delete task |
| GET | `/health` | Health check |
| GET | `/metrics` | Prometheus metrics |

---

## 👨‍💻 DevOps Lifecycle Covered

- ✅ **Plan** — Requirements from PDF spec
- ✅ **Code** — React + Node.js + MongoDB
- ✅ **Build** — Docker multi-stage builds
- ✅ **Test** — Jest unit tests in CI
- ✅ **Release** — Docker Hub image versioning
- ✅ **Deploy** — Kubernetes + Terraform
- ✅ **Operate** — Docker Compose for local
- ✅ **Monitor** — Prometheus + Grafana

---

## 👥 Team

**GitHub:** [Prithvi2400](https://github.com/Prithvi2400)

---

## 📄 License

MIT License — College Project 2025
