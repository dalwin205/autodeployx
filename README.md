# AutoDeployX – CI/CD Pipeline with Rollback

## Overview

AutoDeployX is a simple DevOps project that demonstrates how to automate application deployment using Docker, GitHub Actions, and Kubernetes. The goal is to reduce manual effort and improve reliability through automation and rollback support.

---

## Problem

Manual deployments are slow, error-prone, and difficult to recover from when something goes wrong. Many small projects lack a proper deployment pipeline and rollback mechanism.

---

## Solution

This project implements an automated CI/CD pipeline that:

* Builds and pushes a Docker image on every code change
* Deploys the application to Kubernetes
* Verifies application health
* Supports rollback in case of failure

---

## Architecture

```
Code → GitHub → GitHub Actions → Docker Hub → Kubernetes (Minikube)
```

---

## Tech Stack

* Docker
* GitHub Actions
* Kubernetes (Minikube)
* Node.js

---

## Project Structure

```
autodeployx/
├── app.js
├── package.json
├── Dockerfile
├── deployment.yaml
├── service.yaml
└── .github/workflows/ci-cd.yml
```

---

## Setup

Clone the repository:

```
git clone https://github.com/<your-username>/autodeployx.git
cd autodeployx
```

Run locally:

```
npm install
node app.js
```

Build and push Docker image:

```
docker build -t <your-username>/autodeployx .
docker push <your-username>/autodeployx
```

Start Kubernetes:

```
minikube start
```

Deploy application:

```
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
```

Access the app:

```
minikube service autodeployx-service
```

---

## CI/CD

The pipeline runs on every push and:

* Builds the Docker image
* Pushes it to Docker Hub
* Deploys to Kubernetes

---

## Rollback

If deployment fails:

```
kubectl rollout undo deployment/autodeployx
```

---

## Outcome

* Reduced deployment time
* Removed manual deployment steps
* Improved reliability with rollback

---

## Author

Dalwin
https://github.com/dalwin205

