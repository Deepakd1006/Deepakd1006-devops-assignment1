DevOps Assignment – 3-Tier Application Deployment
Overview

This project demonstrates containerization and deployment of a 3-tier application using Docker and Kubernetes (Minikube).

Frontend: Node.js (Port 3000)
Backend: Spring Boot (Port 8080)
Database: PostgreSQL (Port 5432)
Prerequisites
Docker
Minikube
kubectl
Java 17
Maven
Setup & Execution
1. Start Kubernetes Cluster
minikube start --driver=docker --cpus=2 --memory=4096
kubectl get nodes
2. Build Docker Images
docker build -t banking-backend:v1 ./backend
docker build -t banking-frontend:v1 ./frontend
3. Push Images to Docker Hub
docker login

docker tag banking-backend:v1 <your-username>/banking-backend:v1
docker tag banking-frontend:v1 <your-username>/banking-frontend:v1

docker push <your-username>/banking-backend:v1
docker push <your-username>/banking-frontend:v1
4. Deploy to Kubernetes
kubectl apply -f k8s/
5. Verify Resources
kubectl get pods -n banking-app
kubectl get services -n banking-app
6. Access Application
minikube service frontend -n banking-app
Application Flow

Browser → Frontend → Backend → PostgreSQL

Kubernetes Components
Namespace
Deployments (frontend, backend, postgres)
Services
ConfigMaps
Secrets
Persistent Volume Claim
Result

Application is deployed on Kubernetes with frontend UI, backend APIs, and PostgreSQL database running successfully.