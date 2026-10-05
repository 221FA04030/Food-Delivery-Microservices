                    🚀 MICROSERVICES DEVOPS PROJECT
                       Complete DevOps Implementation

┌──────────────────────────────────────────────────────────────────────────────┐
│  🏗️ ARCHITECTURE                                                             │
│                                                                              │
│  Developer → Git → GitHub → GitHub Actions → Docker → Registry              │
│                                                     ↓                        │
│                                                   Helm                       │
│                                                     ↓                        │
│              Kubernetes → Services → Pods → HPA → Ingress                   │
│                         ↓                         ↓                          │
│                    Prometheus                 Alloy → Loki                  │
│                         ↓                         ↓                          │
│                       Grafana ←─────────────────┘                           │
└──────────────────────────────────────────────────────────────────────────────┘

┌───────────────────────────────┐    ┌────────────────────────────────────────┐
│ 🛠️ TECHNOLOGY STACK           │    │ 📁 PROJECT STRUCTURE                   │
│                               │    │                                        │
│ Git / GitHub      → Source    │    │ project/                               │
│ Docker            → Containers│    │ ├── services/                          │
│ Docker Compose    → Local Run │    │ │   ├── auth-service/                  │
│ Docker Registry   → Images    │    │ │   ├── user-service/                  │
│ Kubernetes        → Orchestration│ │ │   ├── order-service/                 │
│ Minikube          → Local K8s │    │ │   └── payment-service/               │
│ Helm              → Packaging │    │ ├── frontend/                          │
│ GitHub Actions    → CI/CD     │    │ ├── helm/project/                      │
│ Prometheus        → Metrics   │    │ ├── monitoring/                        │
│ Grafana           → Dashboard │    │ ├── logging/                           │
│ Alloy + Loki      → Logging   │    │ ├── .github/workflows/cicd.yml        │
│ HPA               → Scaling   │    │ ├── docker-compose.yml                │
│ Ingress           → Routing   │    │ └── README.md                          │
└───────────────────────────────┘    └────────────────────────────────────────┘

┌──────────────────────────────────────────────────────────────────────────────┐
│ 🔄 COMPLETE DEVOPS WORKFLOW                                                  │
│                                                                              │
│  1. CODE DEVELOPMENT                                                        │
│     ↓                                                                        │
│  2. Git → GitHub                                                             │
│     ↓                                                                        │
│  3. GitHub Actions → Build / Test                                            │
│     ↓                                                                        │
│  4. Docker Build                                                             │
│     ↓                                                                        │
│  5. Push Image → Container Registry                                          │
│     ↓                                                                        │
│  6. Helm → Kubernetes Deployment                                              │
│     ↓                                                                        │
│  7. Kubernetes → Pods / Services / Ingress                                    │
│     ↓                                                                        │
│  8. HPA → Automatic Scaling                                                   │
│     ↓                                                                        │
│  9. Prometheus → Metrics → Grafana                                            │
│     ↓                                                                        │
│ 10. Alloy → Loki → Grafana → Logs                                             │
└──────────────────────────────────────────────────────────────────────────────┘

┌──────────────────────────────┐    ┌──────────────────────────────────────────┐
│ ☸️ KUBERNETES                 │    │ 📊 MONITORING & LOGGING                  │
│                              │    │                                          │
│ Deployment → ReplicaSet      │    │ Prometheus → Metrics                     │
│                    ↓         │    │ Grafana    → Visualization              │
│                   Pods       │    │                                          │
│                              │    │ Metrics Server → CPU/Memory/HPA          │
│ Service    → Networking      │    │ kube-state-metrics → K8s state           │
│ ConfigMap  → Configuration  │    │ Node Exporter → Node metrics             │
│ Secret     → Sensitive data │    │                                          │
│ Ingress    → HTTP routing   │    │ Alloy → Collect logs                     │
│ HPA        → Scaling        │    │ Loki  → Store/query logs                 │
│                              │    │ Grafana → Display logs                   │
└──────────────────────────────┘    └──────────────────────────────────────────┘

┌──────────────────────────────────────────────────────────────────────────────┐
│ 🔐 CONFIGURATION & SECURITY                                                  │
│                                                                              │
│ ConfigMap → Non-sensitive configuration                                      │
│ Secret    → Passwords / API keys / DB credentials                            │
│                                                                              │
│ ❌ Never commit passwords, tokens, API keys, private keys or .env files.      │
│ ✅ Use Kubernetes Secrets + GitHub Secrets + Environment Variables.           │
└──────────────────────────────────────────────────────────────────────────────┘

┌──────────────────────────────────────────────────────────────────────────────┐
│ 🔍 IMPORTANT COMMANDS                                                        │
│                                                                              │
│ Git       : git status | git add . | git commit | git push                   │
│ Docker    : docker build | docker ps | docker logs | docker stop             │
│ Compose   : docker compose up -d | docker compose down                      │
│ Kubernetes: kubectl get pods | kubectl get svc | kubectl logs | kubectl describe│
│ Minikube  : minikube start | minikube status | minikube dashboard            │
│ Helm      : helm lint | helm template | helm install | helm upgrade           │
│ HPA       : kubectl get hpa | kubectl describe hpa | kubectl get hpa -w       │
│ Ingress   : kubectl get ingress | kubectl describe ingress                   │
│ Metrics   : kubectl top nodes | kubectl top pods                             │
└──────────────────────────────────────────────────────────────────────────────┘

┌──────────────────────────────────────────────────────────────────────────────┐
│ ✅ FINAL VERIFICATION                                                        │
│                                                                              │
│ Application ✓   Docker ✓   Registry ✓   Kubernetes ✓   Helm ✓                │
│ CI/CD ✓         HPA ✓      Ingress ✓    Prometheus ✓   Grafana ✓             │
│ Alloy ✓         Loki ✓     Logs ✓       Monitoring ✓                        │
└──────────────────────────────────────────────────────────────────────────────┘

                    🎯 FINAL DEVOPS LIFECYCLE

        CODE → GIT → GITHUB → CI/CD → DOCKER → REGISTRY
             → HELM → KUBERNETES → HPA → MONITORING → LOGGING

                    Chiranjeevi Pasupuleti
                    Aspiring DevOps Engineer
