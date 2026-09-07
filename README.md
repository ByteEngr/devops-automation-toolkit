# A Complete DevOps Project – CI/CD, Kubernetes & Monitoring

An end-to-end **production-style DevOps project** demonstrating how to build,containerize, deploy and monitor a web application using modern DevOps tools and best practices.

---

## Project Overview

This project covers the full DevOps lifecycle:

1. Application development using Python (Flask)
2. Containerization with Docker
3. CI/CD automation using GitHub Actions
4. Deployment to Kubernetes
5. Service exposure via NodePort
6. Monitoring with Prometheus and Grafana

---

---

## Tech Stack

1. **Programming Language:** Python  
2. **Framework:** Flask  
3. **Containerization:** Docker  
4. **CI/CD:** GitHub Actions  
- **Orchestration:** Kubernetes  
- **Monitoring:** Prometheus, Grafana  
- **Local Cluster:** Minikube  

---

## Project Structure

```
├── app
│   ├── app.py
│   ├── Dockerfile
│   └── requirements.txt
├── deployment.yaml
├── k8s
│   └── namespace.yaml
└── service.yaml

2 directories, 6 files
```

---

## Application Details

A simple Flask-based REST API designed for containerized deployment.

### API Endpoints:

| Endpoint | Description |
|---------|-------------|
| `/` | Application status and environment |
| `/health` | Health check endpoint |

---

## Docker:

### Build Image
```bash
docker build -t devops-app ./app
```

### Run Locally
```bash
docker run -p 5000:5000 devops-app
```

---

## CI/CD Pipeline

The GitHub Actions pipeline:

- Triggers on push to `main`
- Builds Docker image
- Pushes image to DockerHub

### Required Secrets

- `DOCKER_USERNAME`
- `DOCKER_PASSWORD`

---

## Kubernetes Deployment

### Start Cluster
```bash
minikube start
```

### Deploy Resources
```bash
kubectl apply -f k8s/namespace.yaml
kubectl apply -f k8s/
```

### Access Application
```bash
minikube service devops-service -n devops-project
```
