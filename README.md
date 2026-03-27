<<<<<<< HEAD
# 3-Tier DevOps Project – Kubernetes Deployment
=======
3-Tier DevOps Project – Kubernetes Deployment
Overview
>>>>>>> b18d7f6cea4f0ec7027ca66b13513345204f64f0

## Overview
This project demonstrates containerization and deployment of a 3-tier application using Docker and Kubernetes (Minikube).

<<<<<<< HEAD
---

## Architecture
- Frontend: Node.js (Express + EJS) – Port 3000  
- Backend: Spring Boot (Java 17) – Port 8080  
- Database: PostgreSQL – Port 5432  

---

## Project Structure
```bash
=======
Architecture
Frontend: Node.js (Express + EJS) – Port 3000
Backend: Spring Boot (Java 17) – Port 8080
Database: PostgreSQL – Port 5432
Project Structure
>>>>>>> b18d7f6cea4f0ec7027ca66b13513345204f64f0
devops-assignment1/
├── frontend/
├── backend/
├── k8s/
└── README.md
<<<<<<< HEAD
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
=======
Prerequisites
Docker
Minikube
kubectl
Java 17
Maven
Setup and Deployment
Start Minikube
minikube start --driver=docker --cpus=2 --memory=4096
kubectl get nodes
Build Docker Images
docker build -t banking-backend:v1 ./backend
docker build -t banking-frontend:v1 ./frontend
Push Images to Docker Hub
>>>>>>> b18d7f6cea4f0ec7027ca66b13513345204f64f0
docker login

docker tag banking-backend:v1 <your-username>/banking-backend:v1
docker tag banking-frontend:v1 <your-username>/banking-frontend:v1

docker push <your-username>/banking-backend:v1
docker push <your-username>/banking-frontend:v1
<<<<<<< HEAD
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
=======
Deploy to Kubernetes
kubectl apply -f k8s/
Verify Deployment
kubectl get pods -n banking-app
kubectl get services -n banking-app
Access Application
>>>>>>> b18d7f6cea4f0ec7027ca66b13513345204f64f0
minikube service frontend -n banking-app
```

---

## Application Flow
```
Browser → Frontend → Backend → PostgreSQL
```

<<<<<<< HEAD
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
=======
Kubernetes Resources
Namespace
Deployments
Services
ConfigMaps
Secrets
Persistent Volume Claim
Result

The application runs on Kubernetes with frontend, backend, and database services successfully deployed and connected.
>>>>>>> b18d7f6cea4f0ec7027ca66b13513345204f64f0
