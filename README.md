# Kubernetes Ingress Lab — Path & Host Routing

## 📝 Overview
This lab demonstrates **Kubernetes Ingress** concepts using **Minikube**:
- Path-based routing  
- Host-based routing  
- PathType: Exact vs Prefix  
- Default backend / catch-all routes  

We have **3 backend services**:
- `webapp-svc`
- `api-svc`
- `admin-svc`  

Ingress allows **external access** to ClusterIP services without exposing NodePorts.

---

## ⚙️ Prerequisites
Enable the Ingress Controller and deploy backend services:

```bash
# Enable ingress on minikube
minikube addons enable ingress

# Wait until controller pod is running
kubectl get pods -n ingress-nginx

# Verify IngressClass exists
kubectl get ingressclass

# Apply backend deployments and ClusterIP services
kubectl apply -f 01-deployments-and-services.yaml

# Confirm deployments and services are ready
kubectl get deploy,svc
