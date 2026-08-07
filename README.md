# AI Platform on Kubernetes

> A production-style AI Platform built using Kubernetes, GitOps, Helm, Kustomize and Infrastructure as Code.

![GitHub](https://img.shields.io/badge/Kubernetes-k3s-blue)
![GitHub](https://img.shields.io/badge/GitOps-ArgoCD-red)
![GitHub](https://img.shields.io/badge/Helm-v3-blue)
![GitHub](https://img.shields.io/badge/Platform-Engineering-success)
![GitHub](https://img.shields.io/badge/AI-Ollama-green)

---

# Project Goal

The objective of this project is to build a modern AI Platform similar to those used by Platform Engineering and MLOps teams.

Rather than simply deploying an LLM, the goal is to build the complete platform around it using GitOps, Kubernetes, monitoring, automation and Infrastructure as Code.

---

# Architecture

```
                        GitHub Repository
                               │
                         Git Push
                               │
                               ▼
                          ArgoCD (GitOps)
                     Detects repository changes
                               │
             ┌─────────────────┴──────────────────┐
             │                                    │
             ▼                                    ▼
       Kustomize                            Helm Charts
             │                                    │
             ▼                                    ▼
      Ollama + OpenWebUI          Prometheus + Grafana
             │
             ▼
        Qwen Language Model
             │
             ▼
          Kubernetes (k3s)
```

---

# Technology Stack

| Technology | Purpose |
|------------|---------|
| Kubernetes (k3s) | Container orchestration |
| ArgoCD | GitOps Continuous Delivery |
| Helm | Package manager for Kubernetes |
| Kustomize | Kubernetes manifest customization |
| Ollama | Local LLM runtime |
| Open WebUI | Chat interface |
| Qwen | Large Language Model |
| Prometheus | Metrics collection |
| Grafana | Monitoring dashboards |
| Terraform | Infrastructure as Code *(coming soon)* |
| GitHub Actions | CI/CD *(coming soon)* |

---

# Repository Structure

```
AI-Platform/

apps/
├── ollama/
├── open-webui/
├── mlflow/
└── sample-api/

gitops/
├── bootstrap/
└── applications/

monitoring/
└── kube-prometheus-stack/

terraform/

architecture/

docs/

scripts/

.github/
```

---

# Current Features

- GitOps deployment using ArgoCD
- Kubernetes deployment using Kustomize
- Helm based monitoring stack
- Ollama deployed inside Kubernetes
- Open WebUI deployed inside Kubernetes
- Persistent storage
- Qwen model installed
- Prometheus monitoring
- Grafana dashboards
- Automatic reconciliation from Git

---

# Deployment Workflow

```
Developer

git push

        │
        ▼

GitHub Repository

        │
        ▼

ArgoCD detects changes

        │
        ▼

Synchronises Kubernetes

        │
        ▼

Application Updated
```

No manual deployments are required after the initial bootstrap.

---

# Monitoring Stack

Deployed using Helm through ArgoCD.

Includes

- Prometheus
- Grafana
- Alertmanager
- kube-state-metrics
- node-exporter

---

# AI Stack

## Ollama

Provides the LLM runtime inside Kubernetes.

## Open WebUI

Provides a browser interface to interact with models.

## Installed Models

- Qwen 2.5 0.5B

---

# GitOps

The platform follows GitOps principles.

Git is the single source of truth.

```
Git
 │
 ▼
ArgoCD
 │
 ▼
Kubernetes
```

Manual changes made directly to Kubernetes are automatically reverted by ArgoCD.

---

# Helm

Third-party applications are installed using Helm.

Current Helm deployments:

- kube-prometheus-stack

---

# Kustomize

Internal applications are deployed using Kustomize.

Current Kustomize applications:

- Ollama
- Open WebUI

---

# Lessons Learned

During development several production-style issues were encountered and resolved.

### Kubernetes

- DiskPressure node taints
- Scheduler failures
- Pod Pending
- CrashLoopBackOff
- Persistent Volumes
- Local Path Storage

### GitOps

- ArgoCD sync issues
- Kustomize path errors
- Repository restructuring

### Platform Engineering

- Containerd image management
- HostPort conflicts
- Node exporter conflicts
- Resource pressure
- Helm chart debugging

---

# Future Roadmap

## Phase 1 ✅

- Kubernetes
- ArgoCD
- Ollama
- Open WebUI
- Prometheus
- Grafana

---

## Phase 2

- FastAPI AI API
- GitHub Actions CI/CD
- Automatic deployments
- Traefik Ingress
- HTTPS

---

## Phase 3

- MLflow
- Vector Database (Qdrant)
- RAG Pipeline
- Authentication
- Multi-model support

---

## Phase 4

- Terraform Infrastructure
- VPS deployment
- Cloudflare
- Production domain
- High Availability

---

# Skills Demonstrated

- Kubernetes
- Platform Engineering
- GitOps
- Helm
- Kustomize
- Observability
- Monitoring
- AI Infrastructure
- Containerisation
- Infrastructure as Code

---

# Screenshots

## ArgoCD

*(Coming Soon)*

---

## Open WebUI

*(Coming Soon)*

---

## Grafana

*(Coming Soon)*

---

## Prometheus

*(Coming Soon)*

---

# Author

**Saeed Ashoor**

Cloud | DevOps | Platform Engineering | AI Infrastructure

GitHub

https://github.com/Sashoor