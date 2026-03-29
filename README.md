# 🚀 Local GitOps Platform  
**kind · Argo CD · Argo Rollouts · Linkerd · Prometheus · Grafana**

![Kubernetes](https://img.shields.io/badge/Kubernetes-GitOps-blue?logo=kubernetes)
![ArgoCD](https://img.shields.io/badge/ArgoCD-GitOps-orange)
![Rollouts](https://img.shields.io/badge/Argo%20Rollouts-Canary-green)
![Linkerd](https://img.shields.io/badge/Linkerd-ServiceMesh-blueviolet)
![Status](https://img.shields.io/badge/Project-Production--Style-success)

---

## 📌 Project Overview

A **production-style Kubernetes platform built locally** to demonstrate:

- GitOps-based deployments  
- Progressive delivery (canary releases)  
- Service-to-service security (mTLS)  
- Observability and monitoring  

👉 Designed to simulate real-world DevOps workflows using a local `kind` cluster.

---

## 🎯 Project Impact

This project demonstrates the ability to:

- Design a GitOps-driven deployment system  
- Implement safe release strategies (canary deployments)  
- Handle deployment failures and rollback scenarios  
- Secure microservices with service mesh (mTLS)  
- Build observability dashboards for debugging systems  

💡 Equivalent to hands-on DevOps / Kubernetes platform experience

---

## 🏗️ Architecture Diagram

> Save your generated image as: `docs/architecture.png`

![Architecture](docs/)

---

## ⚙️ Key Features

### 🔁 GitOps Deployment
- Declarative infrastructure stored in Git  
- Automated sync & self-healing using Argo CD  

---

### 🚦 Progressive Delivery
- Canary deployments using Argo Rollouts  
- Traffic shifting: 10% → 30% → 60% → 100%  
- Pause and controlled promotion  

---

### ❌ Failure Handling
- Simulated faulty deployment  
- Rollout automatically paused  
- Failure observed via metrics  
- Rollback executed  

---

### 🔐 Security
- RBAC and ServiceAccounts  
- NetworkPolicies (default deny model)  
- mTLS using Linkerd  

---

### 📊 Observability
- Metrics collected using Prometheus  
- Dashboards built with Grafana  
- Tracks:
  - CPU / Memory  
  - Pod restarts  
  - Application health  

---

## 📂 Repository Structure

```text
local-gitops-platform/
├─ app-source/
│  ├─ frontend/
│  ├─ api/
│  └─ worker/
│
├─ gitops/
│  ├─ apps/
│  ├─ platform/
│  │  ├─ argocd/
│  │  ├─ argo-rollouts/
│  │  ├─ ingress/
│  │  ├─ linkerd/
│  │  ├─ monitoring/
│  │  ├─ network-policies/
│  │  └─ rbac/
│  └─ projects/
│
├─ docs/
│  └─ architecture.png
│
├─ scripts/
└─ README.md
