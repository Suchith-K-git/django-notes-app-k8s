# Full Stack Notes Application Deployment

## Project Overview

This project demonstrates the deployment and management of a containerized Full Stack Notes Application using Docker, Kubernetes, and AWS EC2.

The application uses a Django backend with a React frontend and is deployed on a Kubernetes cluster running on AWS infrastructure.

> Note: Switch to the `dev` branch before starting the setup.

```bash id="w8m3qn"
git checkout dev
```

---

# Tech Stack

* Docker
* Kubernetes
* AWS EC2
* Django
* React
* Git & GitHub

---

# Project Features

* Containerized application deployment using Docker
* Kubernetes-based application orchestration
* Namespace isolation for application resources
* Service-based communication inside Kubernetes
* Docker image management using Docker Hub
* Source code management using GitHub

---

# Docker Image

Docker Hub Image:

```bash id="u2k7ra"
suchithk/notes-app-k8:latest
```

---

# Kubernetes Components Used

* Namespace
* Deployment
* Service
* Pod
* Port Forwarding

---

# Deployment Steps

## Clone Repository

```bash id="x5n1vd"
git clone <repository-url>
```

---

## Switch to Dev Branch

```bash id="r4m8tp"
git checkout dev
```

---

## Build Docker Image

```bash id="j7q2ls"
docker build -t suchithk/notes-app-k8:latest .
```

---

## Push Docker Image

```bash id="p9w6kc"
docker push suchithk/notes-app-k8:latest
```

---

## Apply Kubernetes Configurations

```bash id="m3x7ru"
kubectl apply -f namespace.yml
kubectl apply -f deployment.yml
kubectl apply -f service.yml
```

---

# Verification Commands

Check Namespace:

```bash id="v6t2qe"
kubectl get ns
```

Check Deployments:

```bash id="a8r4zn"
kubectl get deployments -n notes-app
```

Check Pods:

```bash id="k1m9yc"
kubectl get pods -n notes-app
```

Check Services:

```bash id="f5q8lx"
kubectl get svc -n notes-app
```

---

# Access Application

Run Port Forwarding:

```bash id="t7v3pb"
kubectl port-forward service/notes-app-service -n notes-app 8000:8000 --address 0.0.0.0
```

Open in browser:

```text id="c2n6wd"
http://<EC2-PUBLIC-IP>:8000
```

---

# Resume Description

## Full Stack Notes Application Deployment | Docker, Kubernetes, AWS

* Deployed and managed a containerized Django-React Notes Application on Kubernetes.
* Created Docker images and pushed them to Docker Hub.
* Configured Kubernetes Deployments, Services and Namespaces.
* Managed application deployment on AWS EC2 instances.
* Used Git and GitHub for source code management.
