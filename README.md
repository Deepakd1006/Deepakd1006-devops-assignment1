# 3-Tier DevOps Project – Kubernetes Deployment

## Overview
This project demonstrates containerization and deployment of a 3-tier application using Docker and Kubernetes (Minikube).

---

## Architecture
- Frontend: Node.js (Express + EJS) – Port 3000  
- Backend: Spring Boot (Java 17) – Port 8080  
- Database: PostgreSQL – Port 5432  

---

## Project Structure
```bash
devops-assignment1/
├── frontend/
├── backend/
├── k8s/
└── README.md
```

---

## Prerequisites
- Docker  
- Minikube  
- kubectl  
- Java 17  
- Maven  

---

## Setup and Deployment

### Start Minikube
```bash
minikube start --driver=docker --cpus=2 --memory=4096
kubectl get nodes
```

### Build Docker Images
```bash
docker build -t banking-backend:v1 ./backend
docker build -t banking-frontend:v1 ./frontend
```

### Push Images to Docker Hub
```bash
docker login

docker tag banking-backend:v1 <your-username>/banking-backend:v1
docker tag banking-frontend:v1 <your-username>/banking-frontend:v1

docker push <your-username>/banking-backend:v1
docker push <your-username>/banking-frontend:v1
```

### Deploy to Kubernetes
```bash
kubectl apply -f k8s/
```

### Verify Deployment
```bash
kubectl get pods -n banking-app
kubectl get services -n banking-app
```

### Access Application
```bash
minikube service frontend -n banking-app
```

---

## Application Flow
```
Browser → Frontend → Backend → PostgreSQL
```

---

## Kubernetes Resources
- Namespace  
- Deployments  
- Services  
- ConfigMaps  
- Secrets  
- Persistent Volume Claim  

---

## Result
The application runs on Kubernetes with frontend, backend, and database services successfully deployed and connected.
