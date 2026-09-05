# 🚀 Kubernetes One Shot

> **A hands-on Kubernetes learning repository covering Kubernetes fundamentals, workloads, networking, storage, Helm, custom resources, dashboards, and real-world application deployments.**

![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=for-the-badge\&logo=kubernetes\&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge\&logo=docker\&logoColor=white)
![Helm](https://img.shields.io/badge/Helm-0F1689?style=for-the-badge\&logo=helm\&logoColor=white)
![YAML](https://img.shields.io/badge/YAML-CB171E?style=for-the-badge\&logo=yaml\&logoColor=white)
![DevOps](https://img.shields.io/badge/DevOps-0A0A0A?style=for-the-badge\&logo=devops\&logoColor=white)

---

## 📌 About This Repository

This repository contains my **Kubernetes learning journey and hands-on practice**.

The goal of this repository is to understand Kubernetes from the fundamentals to practical application deployment by working with Kubernetes manifests, workloads, services, storage, Helm, custom resources, and real applications.

Instead of learning Kubernetes only through theory, this repository focuses on:

* 🧠 Understanding Kubernetes concepts
* ⌨️ Practicing `kubectl` commands
* 📄 Writing Kubernetes YAML manifests
* 🚀 Deploying applications
* 🌐 Exposing applications using Services
* 💾 Working with databases and persistent storage
* 📦 Managing applications using Helm
* 🧩 Understanding Custom Resource Definitions
* 🖥️ Working with the Kubernetes Dashboard
* 🐳 Running containerized applications inside Kubernetes
* 🔧 Troubleshooting Kubernetes workloads

---

# 📚 What I Am Learning

This repository covers the following Kubernetes concepts:

### Kubernetes Fundamentals

* What is Kubernetes?
* Why Kubernetes?
* Containers vs Virtual Machines
* Monolithic vs Microservices Architecture
* Kubernetes Architecture
* Control Plane
* Worker Nodes
* Kubernetes API Server
* Scheduler
* Controller Manager
* etcd
* Kubelet
* Kube-proxy
* Container Runtime

### Kubernetes Objects

* Pods
* ReplicaSets
* Deployments
* Services
* Namespaces
* ConfigMaps
* Secrets
* Volumes
* Persistent Volumes
* Persistent Volume Claims
* StatefulSets
* DaemonSets
* Jobs
* CronJobs

### Networking

* ClusterIP
* NodePort
* LoadBalancer
* Service Discovery
* DNS
* Ingress
* Pod-to-Pod Communication

### Configuration & Storage

* ConfigMaps
* Secrets
* Volumes
* PersistentVolumes
* PersistentVolumeClaims
* Storage Concepts

### Application Management

* Rolling Updates
* Rollbacks
* Scaling
* Replica Management
* Health Checks
* Resource Management

### Advanced Kubernetes

* Helm
* Custom Resource Definitions
* Kubernetes Dashboard
* Stateful Applications
* Application Deployment
* Containerized Application Management

---

# 🗂️ Repository Structure

```text
Kubernetes-one-shot/
│
├── apache/
│   └── Apache related Kubernetes manifests
│
├── crd/
│   └── Custom Resource Definition examples
│
├── dashboard/
│   └── Kubernetes Dashboard configuration
│
├── django-notes-app/
│   └── Django application deployment
│
├── helm/
│   └── Helm charts and Kubernetes package management
│
├── mysql/
│   └── MySQL deployment and configuration
│
├── nginx/
│   └── NGINX deployment and service examples
│
├── pods/
│   └── Kubernetes Pod examples
│
└── README.md
```

The directory structure reflects the current repository organization.

---

# 🧰 Tools & Technologies

The following tools are used throughout this repository:

| Technology | Purpose                      |
| ---------- | ---------------------------- |
| Kubernetes | Container orchestration      |
| Docker     | Containerization             |
| kubectl    | Kubernetes command-line tool |
| Helm       | Kubernetes package manager   |
| YAML       | Kubernetes configuration     |
| NGINX      | Web server                   |
| Apache     | Web server                   |
| MySQL      | Relational database          |
| Django     | Python web application       |
| Git        | Version control              |
| GitHub     | Source code management       |

---

# ⚙️ Prerequisites

Before using this repository, install the following:

* Docker
* Kubernetes
* kubectl
* Helm
* Git

For local Kubernetes practice, you can use one of the following:

* Minikube
* Kind
* Docker Desktop Kubernetes
* A cloud Kubernetes service such as AWS EKS, Azure AKS, or Google GKE

---

# 🚀 Getting Started

## 1. Clone the Repository

```bash
git clone https://github.com/HussnainAshiq-5657/Kubernetes-one-shot.git
```

Move into the repository:

```bash
cd Kubernetes-one-shot
```

---

# ☸️ Verify Kubernetes

Check your Kubernetes client:

```bash
kubectl version --client
```

Check cluster information:

```bash
kubectl cluster-info
```

Check available nodes:

```bash
kubectl get nodes
```

Check all namespaces:

```bash
kubectl get namespaces
```

---

# 🐳 Kubernetes + Docker

Kubernetes commonly runs containerized workloads.

The general workflow is:

```text
Application
     ↓
Dockerfile
     ↓
Docker Image
     ↓
Container Registry
     ↓
Kubernetes
     ↓
Pod
     ↓
Service
     ↓
User
```

For example:

```text
Django Application
       ↓
Docker Image
       ↓
Kubernetes Deployment
       ↓
Pods
       ↓
Service
       ↓
Application Access
```

---

# 🟦 1. Pods

A **Pod** is the smallest deployable unit in Kubernetes.

A Pod usually contains one application container, although a Pod can contain multiple tightly coupled containers.

Check Pods:

```bash
kubectl get pods
```

Check Pods in all namespaces:

```bash
kubectl get pods -A
```

Get detailed information:

```bash
kubectl describe pod <pod-name>
```

View logs:

```bash
kubectl logs <pod-name>
```

Execute a command inside a container:

```bash
kubectl exec -it <pod-name> -- /bin/bash
```

Create a simple NGINX Pod:

```bash
kubectl run nginx --image=nginx
```

Delete a Pod:

```bash
kubectl delete pod nginx
```

---

# 🟩 2. Namespaces

Namespaces provide logical isolation inside a Kubernetes cluster.

Create a namespace:

```bash
kubectl create namespace dev
```

List namespaces:

```bash
kubectl get namespaces
```

Use a namespace:

```bash
kubectl get pods -n dev
```

Delete a namespace:

```bash
kubectl delete namespace dev
```

Example:

```text
Cluster
│
├── development
│   ├── Pods
│   ├── Services
│   └── Deployments
│
├── production
│   ├── Pods
│   ├── Services
│   └── Deployments
│
└── monitoring
    ├── Prometheus
    └── Grafana
```

---

# 🟨 3. Deployments

Deployments provide declarative management of application Pods.

Create a Deployment:

```bash
kubectl apply -f deployment.yaml
```

Check Deployments:

```bash
kubectl get deployments
```

Check ReplicaSets:

```bash
kubectl get replicasets
```

Scale a Deployment:

```bash
kubectl scale deployment <deployment-name> --replicas=3
```

Check rollout status:

```bash
kubectl rollout status deployment/<deployment-name>
```

View rollout history:

```bash
kubectl rollout history deployment/<deployment-name>
```

Rollback:

```bash
kubectl rollout undo deployment/<deployment-name>
```

---

# 🌐 4. Services

Pods are ephemeral, so Kubernetes Services provide a stable way to access applications.

Main Service types:

```text
ClusterIP
NodePort
LoadBalancer
ExternalName
```

Check Services:

```bash
kubectl get services
```

Create a Service:

```bash
kubectl apply -f service.yaml
```

Inspect a Service:

```bash
kubectl describe service <service-name>
```

Example architecture:

```text
                 ┌──────────────┐
                 │    Client    │
                 └──────┬───────┘
                        │
                        ▼
                 ┌──────────────┐
                 │   Service    │
                 └──────┬───────┘
                        │
             ┌──────────┼──────────┐
             ▼          ▼          ▼
           Pod        Pod        Pod
```

---

# 🌍 5. NGINX

The `nginx/` directory contains Kubernetes practice involving NGINX.

Typical workflow:

```bash
kubectl apply -f nginx/
```

Check resources:

```bash
kubectl get all
```

Check NGINX Pods:

```bash
kubectl get pods
```

Check the Service:

```bash
kubectl get svc
```

View logs:

```bash
kubectl logs <nginx-pod>
```

---

# 🗄️ 6. MySQL

The `mysql/` directory contains Kubernetes practice for deploying MySQL.

This section is useful for understanding how Kubernetes handles stateful applications.

Typical concepts include:

* MySQL Deployment/Stateful workload
* Environment variables
* ConfigMaps
* Secrets
* Services
* Persistent storage

Apply manifests:

```bash
kubectl apply -f mysql/
```

Check resources:

```bash
kubectl get all
```

Check MySQL Pods:

```bash
kubectl get pods
```

Check Services:

```bash
kubectl get svc
```

View logs:

```bash
kubectl logs <mysql-pod>
```

---

# 💾 7. Persistent Storage

Databases require persistent storage.

Important Kubernetes storage concepts:

```text
StorageClass
     ↓
PersistentVolume
     ↓
PersistentVolumeClaim
     ↓
Pod
     ↓
Application
```

Check Persistent Volumes:

```bash
kubectl get pv
```

Check Persistent Volume Claims:

```bash
kubectl get pvc
```

Check StorageClasses:

```bash
kubectl get storageclass
```

The important distinction is:

* **PV** → Actual storage resource
* **PVC** → Request for storage
* **StorageClass** → Defines how storage can be dynamically provisioned

---

# 🔐 8. ConfigMaps & Secrets

## ConfigMap

ConfigMaps store non-sensitive configuration.

Example:

```bash
kubectl create configmap app-config \
  --from-literal=APP_ENV=development
```

View ConfigMaps:

```bash
kubectl get configmaps
```

---

## Secret

Secrets are designed for sensitive configuration such as:

* Passwords
* API keys
* Tokens
* Credentials

Create a Secret:

```bash
kubectl create secret generic app-secret \
  --from-literal=username=admin \
  --from-literal=password=password
```

View Secrets:

```bash
kubectl get secrets
```

> Never commit real passwords, API keys, tokens, or production credentials to GitHub.

---

# 🐍 9. Django Notes Application

The `django-notes-app/` directory contains a practical application deployment.

This demonstrates how a real application can be moved from:

```text
Local Application
       ↓
Docker Container
       ↓
Kubernetes Deployment
       ↓
Pods
       ↓
Service
       ↓
Application
```

Typical Kubernetes workflow:

```bash
kubectl apply -f django-notes-app/
```

Check the deployment:

```bash
kubectl get deployments
```

Check Pods:

```bash
kubectl get pods
```

Check Services:

```bash
kubectl get svc
```

Check logs:

```bash
kubectl logs <pod-name>
```

---

# 📦 10. Helm

Helm is a package manager for Kubernetes.

Instead of manually managing many YAML files, Helm allows Kubernetes applications to be packaged into reusable charts.

Basic Helm commands:

```bash
helm version
```

List installed releases:

```bash
helm list
```

Create a chart:

```bash
helm create my-chart
```

Install a chart:

```bash
helm install my-app ./my-chart
```

Upgrade:

```bash
helm upgrade my-app ./my-chart
```

Uninstall:

```bash
helm uninstall my-app
```

The Helm directory in this repository is used to practice Kubernetes application packaging and deployment.

---

# 🧩 11. Custom Resource Definitions — CRD

Kubernetes can be extended using **Custom Resource Definitions (CRDs)**.

CRDs allow you to define your own Kubernetes resource types.

Example:

```text
Built-in Resources

Pod
Deployment
Service
ConfigMap
Secret

        +

Custom Resources

MyApplication
Database
Backup
```

Check installed CRDs:

```bash
kubectl get crd
```

Apply a CRD:

```bash
kubectl apply -f crd/
```

Inspect a CRD:

```bash
kubectl describe crd <crd-name>
```

---

# 🖥️ 12. Kubernetes Dashboard

The `dashboard/` directory is used for Kubernetes Dashboard practice.

A dashboard provides a graphical way to inspect Kubernetes resources.

You can use it to understand:

* Nodes
* Pods
* Deployments
* Services
* Namespaces
* Workloads
* Resource usage

The command used to access the dashboard depends on the Kubernetes installation and Dashboard version.

---

# 🌐 13. Apache

The `apache/` directory contains Apache HTTP Server deployment practice.

The basic Kubernetes workflow is:

```text
Apache Image
     ↓
Pod
     ↓
Deployment
     ↓
Service
     ↓
Client
```

Apply the manifests:

```bash
kubectl apply -f apache/
```

Check resources:

```bash
kubectl get all
```

---

# 🔍 14. Essential kubectl Commands

## Cluster

```bash
kubectl cluster-info
kubectl get nodes
kubectl describe node <node-name>
```

## Pods

```bash
kubectl get pods
kubectl get pods -o wide
kubectl describe pod <pod-name>
kubectl logs <pod-name>
kubectl delete pod <pod-name>
```

## Deployments

```bash
kubectl get deployments
kubectl describe deployment <deployment-name>
kubectl scale deployment <deployment-name> --replicas=3
```

## Services

```bash
kubectl get svc
kubectl describe svc <service-name>
```

## Namespaces

```bash
kubectl get ns
kubectl create ns <namespace>
kubectl delete ns <namespace>
```

## All Resources

```bash
kubectl get all
```

All namespaces:

```bash
kubectl get all -A
```

---

# 🛠️ 15. Troubleshooting Kubernetes

When a Kubernetes application is not working, I follow a systematic debugging process.

## Step 1 — Check Pods

```bash
kubectl get pods
```

Look for states such as:

```text
Running
Pending
CrashLoopBackOff
ImagePullBackOff
ErrImagePull
Completed
```

---

## Step 2 — Describe the Pod

```bash
kubectl describe pod <pod-name>
```

Check the **Events** section.

---

## Step 3 — Check Logs

```bash
kubectl logs <pod-name>
```

For a previous crashed container:

```bash
kubectl logs <pod-name> --previous
```

---

## Step 4 — Check Deployment

```bash
kubectl get deployment
kubectl describe deployment <deployment-name>
```

---

## Step 5 — Check Service

```bash
kubectl get svc
kubectl describe svc <service-name>
```

---

## Step 6 — Check Endpoints

```bash
kubectl get endpoints
```

---

## Step 7 — Enter the Container

```bash
kubectl exec -it <pod-name> -- /bin/bash
```

If Bash is unavailable:

```bash
kubectl exec -it <pod-name> -- /bin/sh
```

---

# 🔄 Kubernetes Deployment Workflow

A typical Kubernetes application deployment looks like this:

```text
             Developer
                 │
                 ▼
             GitHub
                 │
                 ▼
             Dockerfile
                 │
                 ▼
            Docker Image
                 │
                 ▼
          Container Registry
                 │
                 ▼
        Kubernetes Deployment
                 │
                 ▼
               Pods
                 │
                 ▼
              Service
                 │
                 ▼
              Ingress
                 │
                 ▼
               Users
```

---

# 🏗️ Kubernetes Architecture

```text
                     Kubernetes Cluster
                            │
          ┌─────────────────┴─────────────────┐
          │                                   │
     Control Plane                         Worker Nodes
          │                                   │
    ┌─────┼─────┐                     ┌───────┼───────┐
    │     │     │                     │       │       │
 API   Scheduler Controller          Pod     Pod     Pod
Server          Manager
    │
   etcd
```

### Control Plane

Responsible for managing the cluster.

Major components:

* API Server
* Scheduler
* Controller Manager
* etcd

### Worker Node

Runs application workloads.

Major components:

* Kubelet
* Kube-proxy
* Container Runtime
* Pods

---

# 📈 Scaling

Kubernetes makes it easy to increase or decrease application replicas.

Scale to 3 replicas:

```bash
kubectl scale deployment nginx --replicas=3
```

Check:

```bash
kubectl get pods
```

Scale down:

```bash
kubectl scale deployment nginx --replicas=1
```

---

# 🔁 Rolling Updates & Rollbacks

Kubernetes Deployments support rolling updates.

Check rollout:

```bash
kubectl rollout status deployment/nginx
```

View history:

```bash
kubectl rollout history deployment/nginx
```

Rollback:

```bash
kubectl rollout undo deployment/nginx
```

This allows applications to be updated with minimal disruption.

---

# ❤️ Health Checks

Kubernetes supports application health checks.

### Liveness Probe

Determines whether a container is still alive.

### Readiness Probe

Determines whether a container is ready to receive traffic.

### Startup Probe

Helps applications that require additional startup time.

Example:

```yaml
livenessProbe:
  httpGet:
    path: /
    port: 80
  initialDelaySeconds: 10
  periodSeconds: 10
```

---

# 📊 Resource Management

Kubernetes allows CPU and memory resources to be defined.

Example:

```yaml
resources:
  requests:
    cpu: "100m"
    memory: "128Mi"

  limits:
    cpu: "500m"
    memory: "512Mi"
```

### Requests

The amount of resources Kubernetes guarantees for the container.

### Limits

The maximum resources the container is allowed to consume.

---

# 🔐 Kubernetes Security Topics

Important security areas to learn further:

* RBAC
* Service Accounts
* Secrets
* Network Policies
* Pod Security
* Least Privilege
* Container Security
* Image Security
* Kubernetes API Security

---

# 🧪 Hands-On Learning Approach

I am following a practical learning methodology:

```text
Learn Concept
     ↓
Write YAML
     ↓
Deploy Resource
     ↓
Inspect Resource
     ↓
Break Something
     ↓
Troubleshoot
     ↓
Fix It
     ↓
Document It
```

This approach helps convert Kubernetes theory into practical DevOps skills.

---

# 🎯 Learning Roadmap

## Phase 1 — Fundamentals

* [x] What is Kubernetes?
* [x] Kubernetes Architecture
* [x] Pods
* [x] Namespaces
* [x] kubectl
* [x] YAML manifests

## Phase 2 — Workloads

* [x] Deployments
* [x] ReplicaSets
* [ ] StatefulSets
* [ ] DaemonSets
* [ ] Jobs
* [ ] CronJobs

## Phase 3 — Networking

* [x] Services
* [ ] ClusterIP
* [ ] NodePort
* [ ] LoadBalancer
* [ ] Ingress
* [ ] Network Policies
* [ ] Kubernetes DNS

## Phase 4 — Configuration & Storage

* [ ] ConfigMaps
* [ ] Secrets
* [ ] Volumes
* [ ] PersistentVolumes
* [ ] PersistentVolumeClaims
* [ ] StorageClasses

## Phase 5 — Advanced Kubernetes

* [x] Helm
* [x] CRDs
* [x] Kubernetes Dashboard
* [ ] RBAC
* [ ] Resource Management
* [ ] Health Probes
* [ ] Autoscaling
* [ ] Scheduling

## Phase 6 — DevOps Integration

* [ ] Docker
* [ ] CI/CD
* [ ] Jenkins
* [ ] GitHub Actions
* [ ] AWS EKS
* [ ] Terraform
* [ ] Ansible
* [ ] Prometheus
* [ ] Grafana

---

# 💼 Why I Created This Repository

I created this repository to build practical Kubernetes knowledge as part of my **DevOps learning journey**.

The objective is not only to memorize Kubernetes commands but to understand how Kubernetes is used to:

* Deploy applications
* Scale workloads
* Manage containers
* Expose applications
* Store application data
* Configure applications
* Package deployments
* Troubleshoot failures
* Build cloud-native infrastructure

---

# 📌 Kubernetes Interview Preparation

Some important Kubernetes interview topics I am practicing:

### Beginner

1. What is Kubernetes?
2. What is a Pod?
3. What is a Node?
4. What is a Cluster?
5. What is `kubectl`?
6. What is a Namespace?
7. What is a Deployment?
8. What is a ReplicaSet?
9. What is a Service?

### Intermediate

10. Deployment vs StatefulSet
11. Deployment vs ReplicaSet
12. ClusterIP vs NodePort vs LoadBalancer
13. ConfigMap vs Secret
14. PV vs PVC
15. Readiness vs Liveness Probe
16. Rolling Update vs Recreate
17. What happens when a Pod crashes?
18. How does Kubernetes perform service discovery?
19. How does Kubernetes schedule Pods?
20. What is Helm?

### Advanced

21. Explain Kubernetes architecture.
22. What happens internally when `kubectl apply` is executed?
23. How does the Kubernetes Scheduler work?
24. How does Kubernetes maintain the desired state?
25. What is etcd?
26. What is RBAC?
27. What are CRDs?
28. How does Kubernetes networking work?
29. How would you troubleshoot `CrashLoopBackOff`?
30. How would you troubleshoot `ImagePullBackOff`?
31. How would you troubleshoot a Service that cannot reach a Pod?
32. How would you deploy Kubernetes applications in production?

---

# 🧑‍💻 Useful Commands Cheat Sheet

```bash
# Cluster
kubectl cluster-info
kubectl get nodes

# Pods
kubectl get pods
kubectl get pods -A
kubectl get pods -o wide
kubectl describe pod <pod>
kubectl logs <pod>
kubectl exec -it <pod> -- /bin/bash

# Deployments
kubectl get deployments
kubectl describe deployment <deployment>
kubectl scale deployment <deployment> --replicas=3
kubectl rollout status deployment/<deployment>
kubectl rollout undo deployment/<deployment>

# Services
kubectl get svc
kubectl describe svc <service>

# Namespaces
kubectl get ns
kubectl create ns <namespace>

# ConfigMaps
kubectl get configmaps
kubectl describe configmap <configmap>

# Secrets
kubectl get secrets
kubectl describe secret <secret>

# Storage
kubectl get pv
kubectl get pvc
kubectl get storageclass

# CRDs
kubectl get crd

# Resources
kubectl get all
kubectl get all -A

# Apply/Delete
kubectl apply -f <file.yaml>
kubectl delete -f <file.yaml>
```

---

# 📖 Recommended Learning Order

If you are using this repository to learn Kubernetes from scratch, follow this order:

```text
1. Docker Basics
       ↓
2. Kubernetes Architecture
       ↓
3. kubectl
       ↓
4. Pods
       ↓
5. Namespaces
       ↓
6. Deployments
       ↓
7. ReplicaSets
       ↓
8. Services
       ↓
9. ConfigMaps
       ↓
10. Secrets
       ↓
11. Volumes / PV / PVC
       ↓
12. StatefulSets
       ↓
13. Ingress
       ↓
14. Helm
       ↓
15. CRDs
       ↓
16. Security / RBAC
       ↓
17. Monitoring
       ↓
18. CI/CD
       ↓
19. Cloud Kubernetes
```

---

# 🌟 Future Improvements

I plan to continue expanding this repository with:

* [ ] Kubernetes Ingress
* [ ] StatefulSets
* [ ] DaemonSets
* [ ] Jobs & CronJobs
* [ ] ConfigMaps & Secrets
* [ ] PV/PVC
* [ ] RBAC
* [ ] Network Policies
* [ ] HPA
* [ ] Kubernetes Monitoring
* [ ] Prometheus
* [ ] Grafana
* [ ] Jenkins + Kubernetes
* [ ] GitHub Actions + Kubernetes
* [ ] ArgoCD
* [ ] AWS EKS
* [ ] Terraform + Kubernetes
* [ ] Production-grade Kubernetes project

---

# 📚 Useful Resources

* [Kubernetes Documentation](https://kubernetes.io/docs/)
* [Kubernetes GitHub](https://github.com/kubernetes/kubernetes)
* [Helm Documentation](https://helm.sh/docs/)
* [Docker Documentation](https://docs.docker.com/)

---

# 🤝 Contributions

This repository is primarily my personal Kubernetes learning repository, but suggestions and improvements are welcome.

If you find an issue or have an improvement:

1. Fork the repository
2. Create a new branch
3. Make your changes
4. Commit your changes
5. Open a Pull Request

---

# ⭐ Support

If this repository helps you learn Kubernetes, consider giving it a ⭐.

Your feedback and suggestions are always welcome.

---

# 👨‍💻 Author

**Hussnain Ashiq**

GitHub:

[![GitHub](https://img.shields.io/badge/GitHub-HussnainAshiq--5657-181717?style=for-the-badge\&logo=github)](https://github.com/HussnainAshiq-5657)

---

## 🚀 Keep Learning. Keep Building. Keep Deploying.

> **The best way to learn Kubernetes is to deploy something, break it, troubleshoot it, and deploy it again.**

**Kubernetes → Docker → Helm → CI/CD → Cloud → DevOps**
