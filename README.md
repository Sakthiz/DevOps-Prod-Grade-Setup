# 🚀 DevOps Production-Grade Setup - MERN App Deployment

This repository showcases a complete end-to-end **DevOps pipeline** to deploy a production-ready MERN application using industry best practices. It includes **Docker, CI/CD, Infrastructure as Code (Terraform), AWS Cloud, and Monitoring Stack**.

---

## 🧩 Project Overview

- 🖥️ **Application Type**: MERN Stack (Frontend + Backend + MongoDB)
- 🐳 **Containerization**: Docker & Docker Compose
- ⚙️ **CI/CD**: GitHub Actions + Amazon ECR
- ☁️ **Cloud Provider**: AWS (Free Tier)
- 📦 **Infra Provisioning**: Terraform (IaC)
- 📊 **Monitoring**: Prometheus + Grafana + Node Exporter
- 🔐 **Secrets Management**: GitHub Actions Secrets

---

## 🛠️ Tech Stack

| Tool               | Purpose                              |
|--------------------|--------------------------------------|
| **Docker**         | Containerization                     |
| **Docker Compose** | Local & cloud service orchestration  |
| **GitHub Actions** | CI/CD pipeline automation            |
| **AWS EC2**        | Application Hosting                  |
| **Amazon ECR**     | Container Image Registry             |
| **Terraform**      | Infrastructure as Code               |
| **Prometheus**     | Metrics scraping                     |
| **Grafana**        | Real-time dashboards                 |
| **Node Exporter**  | System metrics monitoring            |

---

## 🧱 Folder Structure

```bash
DevOps-Prod-Grade-Setup/
├── .github/
│   └── workflows/
│       └── build-and-push.yml          # GitHub Actions workflow
├── ec2/                                # EC2-specific deployment setup
│   ├── docker-compose.yml              # Compose for backend, frontend, monitoring                          # Env vars used during EC2 deployment
│   └── prometheus/
│       └── prometheus.yml              # Prometheus scrape configuration
├── backend/                            # Node.js backend (Express)
│   ├── Dockerfile
│   ├── app.js
│   ├── package.json
│   └── package-lock.json
├── frontend/                           # React frontend (Vite)
│   ├── Dockerfile
│   ├── index.html
│   ├── vite.config.js
│   ├── package.json
│   ├── package-lock.json
│   └── src/
│       ├── App.css
│       ├── App.jsx
│       ├── index.css
│       └── main.jsx
├── docker-compose.yml                  # Main Compose for app
└── README.md                           # Project overview
```

---

## 🧱 DevOps Architecture

![image](https://github.com/user-attachments/assets/29b84aa4-ba4d-42c9-a00b-47533e84e012)

---

## 🔁 CI/CD Workflow

This repository includes a GitHub Actions pipeline that:

1. **Builds Docker images** for both frontend and backend.
2. **Pushes** them to **Amazon ECR**.
3. You then **pull & deploy** them via Docker Compose on EC2.


---

## ☁️ Infrastructure Setup (Terraform)

Refer : https://github.com/Sakthiz/DevOps-Infra-Setup

1. **Creates an EC2 instance**
2. **Provisions security groups**
3. **Generates outputs** (like Public IP)

🔑 Uses variables to avoid hardcoding values and supports secret-free versioning.

---

### 🚀 Deployment Instructions

#### ✅ Deploying Locally

# Create an application directory
mkdir app && cd app

# Create the Docker Compose file
nano docker-compose.yml

✏️ Paste the `docker-compose.yml` content from the  root directory in the repository into this file.

# Build and start the application
docker-compose up -d --build

---
#### 🖥️ Deploying on an EC2 Instance

To simulate a real-world production environment, I provisioned an EC2 instance using Terraform and deployed the entire application and monitoring stack using a single Docker Compose file.

All configurations and files used in the EC2 instance have been added to the repo under the ec2/ folder for review and reproducibility.


# Create an application directory
mkdir app && cd app

# Create the Docker Compose file
nano docker-compose.yml

The docker-compose.yml file for application setup is located at: EC2/app/docker-compose.yml

This file defines and orchestrates all services required to run the application using Docker Compose. It ensures seamless integration and deployment of components like the frontend, backend, and supporting services.

# Pull the container images from ECR
docker-compose pull

# Start the application
docker-compose up -d

---
### ✅ Notes:
* Ensure Docker and Docker Compose are installed on your EC2 instance.
* Open the required ports in your EC2 security group (e.g., 80, 4657).
* Make sure the `docker-compose.yml` references the correct ECR image URLs.

---
## 🧪 Monitoring with Prometheus & Grafana

### 🔹 Services:

* `Prometheus`: http://<EC2_IP>:9090
* `Grafana`: http://<EC2_IP>:3000
  (Default login: `admin` / `admin`)

### 🔹 Dashboards:

* Custom dashboards for CPU, memory, and container metrics
* Prometheus scrapers:
   Backend /metricks endpoint
   Node Exporter

### 🔹 File:

 The Prometheus monitoring setup is available in the repository.
You can find the configuration file at: EC2/app/prometheus/prometheus.yml

---

# Key Highlights

✅ Production-ready Dockerfiles
✅ Multi-stage builds (frontend)
✅ CI/CD pipeline with ECR integration
✅ Infrastructure as Code (Terraform)
✅ Monitoring stack to track health and metrics
✅ Clear folder structure and modularization

---
## 🏁 Conclusion

This project demonstrates my ability to:

* Build secure, automated, scalable pipelines
* Manage infrastructure using Terraform
* Monitor services using Grafana + Prometheus
* Work with AWS services in a production-grade environment

🎯 Goal: Build & deploy a fully working MERN application on AWS using best DevOps practices.

---

## 🤝 Let’s Connect

📧 Email: [sakthimanikandan1718@gmail.com]
🔗 LinkedIn: [[linkedin.com/in/sakthi-manikandan-a](https://www.linkedin.com/in/sakthi-manikandan-a-79101b23b?utm_source=share&utm_campaign=share_via&utm_content=profile&utm_medium=android_app)]
🔗 GitHub: [[github.com/Sakthiz](https://github.com/Sakthiz)]

---

*“Build like an engineer, think like an SRE.”*


