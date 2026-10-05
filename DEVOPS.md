Microservices DevOps Platform
A production-style microservices application with a complete DevOps lifecycle covering containerization, orchestration, CI/CD, monitoring, logging, autoscaling, and ingress.
Architecture
#chatgpt-mermaid-_r_eju_{font-family:-apple-system-body,ui-sans-serif,-apple-system,system-ui,"Segoe UI","Helvetica","Apple Color Emoji","Arial",sans-serif,"Segoe UI Emoji","Segoe UI Symbol";font-size:16px;fill:rgb(13, 13, 13);}@keyframes edge-animation-frame{from{stroke-dashoffset:0;}}@keyframes dash{to{stroke-dashoffset:0;}}#chatgpt-mermaid-_r_eju_ .edge-animation-slow{stroke-dasharray:9,5!important;stroke-dashoffset:900;animation:dash 50s linear infinite;stroke-linecap:round;}#chatgpt-mermaid-_r_eju_ .edge-animation-fast{stroke-dasharray:9,5!important;stroke-dashoffset:900;animation:dash 20s linear infinite;stroke-linecap:round;}#chatgpt-mermaid-_r_eju_ .error-icon{fill:rgb(243, 243, 243);}#chatgpt-mermaid-_r_eju_ .error-text{fill:rgb(13, 13, 13);stroke:rgb(13, 13, 13);}#chatgpt-mermaid-_r_eju_ .edge-thickness-normal{stroke-width:1px;}#chatgpt-mermaid-_r_eju_ .edge-thickness-thick{stroke-width:3.5px;}#chatgpt-mermaid-_r_eju_ .edge-pattern-solid{stroke-dasharray:0;}#chatgpt-mermaid-_r_eju_ .edge-thickness-invisible{stroke-width:0;fill:none;}#chatgpt-mermaid-_r_eju_ .edge-pattern-dashed{stroke-dasharray:3;}#chatgpt-mermaid-_r_eju_ .edge-pattern-dotted{stroke-dasharray:2;}#chatgpt-mermaid-_r_eju_ .marker{fill:rgb(143, 143, 143);stroke:rgb(143, 143, 143);}#chatgpt-mermaid-_r_eju_ .marker.cross{stroke:rgb(143, 143, 143);}#chatgpt-mermaid-_r_eju_ svg{font-family:-apple-system-body,ui-sans-serif,-apple-system,system-ui,"Segoe UI","Helvetica","Apple Color Emoji","Arial",sans-serif,"Segoe UI Emoji","Segoe UI Symbol";font-size:16px;}#chatgpt-mermaid-_r_eju_ p{margin:0;}#chatgpt-mermaid-_r_eju_ .label{font-family:-apple-system-body,ui-sans-serif,-apple-system,system-ui,"Segoe UI","Helvetica","Apple Color Emoji","Arial",sans-serif,"Segoe UI Emoji","Segoe UI Symbol";color:rgb(13, 13, 13);}#chatgpt-mermaid-_r_eju_ .cluster-label text{fill:rgb(13, 13, 13);}#chatgpt-mermaid-_r_eju_ .cluster-label span{color:rgb(13, 13, 13);}#chatgpt-mermaid-_r_eju_ .cluster-label span p{background-color:transparent;}#chatgpt-mermaid-_r_eju_ .label text,#chatgpt-mermaid-_r_eju_ span{fill:rgb(13, 13, 13);color:rgb(13, 13, 13);}#chatgpt-mermaid-_r_eju_ .node rect,#chatgpt-mermaid-_r_eju_ .node circle,#chatgpt-mermaid-_r_eju_ .node ellipse,#chatgpt-mermaid-_r_eju_ .node polygon,#chatgpt-mermaid-_r_eju_ .node path{fill:rgb(222, 234, 251);stroke:rgb(83, 154, 248);stroke-width:1px;}#chatgpt-mermaid-_r_eju_ .rough-node .label text,#chatgpt-mermaid-_r_eju_ .node .label text,#chatgpt-mermaid-_r_eju_ .image-shape .label,#chatgpt-mermaid-_r_eju_ .icon-shape .label{text-anchor:middle;}#chatgpt-mermaid-_r_eju_ .node .katex path{fill:#000;stroke:#000;stroke-width:1px;}#chatgpt-mermaid-_r_eju_ .rough-node .label,#chatgpt-mermaid-_r_eju_ .node .label,#chatgpt-mermaid-_r_eju_ .image-shape .label,#chatgpt-mermaid-_r_eju_ .icon-shape .label{text-align:center;}#chatgpt-mermaid-_r_eju_ .node.clickable{cursor:pointer;}#chatgpt-mermaid-_r_eju_ .root .anchor path{fill:rgb(143, 143, 143)!important;stroke-width:0;stroke:rgb(143, 143, 143);}#chatgpt-mermaid-_r_eju_ .arrowheadPath{fill:rgb(143, 143, 143);}#chatgpt-mermaid-_r_eju_ .edgePath .path{stroke:rgb(143, 143, 143);stroke-width:1px;}#chatgpt-mermaid-_r_eju_ .flowchart-link{stroke:rgb(143, 143, 143);fill:none;}#chatgpt-mermaid-_r_eju_ .edgeLabel{background-color:rgb(252, 252, 252);text-align:center;}#chatgpt-mermaid-_r_eju_ .edgeLabel p{background-color:rgb(252, 252, 252);}#chatgpt-mermaid-_r_eju_ .edgeLabel rect{opacity:0.5;background-color:rgb(252, 252, 252);fill:rgb(252, 252, 252);}#chatgpt-mermaid-_r_eju_ .labelBkg{background-color:rgba(252, 252, 252, 0.5);}#chatgpt-mermaid-_r_eju_ .cluster rect{fill:rgb(243, 243, 243);stroke:rgba(0, 0, 0, 0.1);stroke-width:1px;}#chatgpt-mermaid-_r_eju_ .cluster text{fill:rgb(13, 13, 13);}#chatgpt-mermaid-_r_eju_ .cluster span{color:rgb(13, 13, 13);}#chatgpt-mermaid-_r_eju_ div.mermaidTooltip{position:absolute;text-align:center;max-width:200px;padding:2px;font-family:-apple-system-body,ui-sans-serif,-apple-system,system-ui,"Segoe UI","Helvetica","Apple Color Emoji","Arial",sans-serif,"Segoe UI Emoji","Segoe UI Symbol";font-size:12px;background:rgb(243, 243, 243);border:1px solid rgba(0, 0, 0, 0.1);border-radius:2px;pointer-events:none;z-index:100;}#chatgpt-mermaid-_r_eju_ .flowchartTitleText{text-anchor:middle;font-size:18px;fill:rgb(13, 13, 13);}#chatgpt-mermaid-_r_eju_ rect.text{fill:none;stroke-width:0;}#chatgpt-mermaid-_r_eju_ .icon-shape,#chatgpt-mermaid-_r_eju_ .image-shape{background-color:rgb(252, 252, 252);text-align:center;}#chatgpt-mermaid-_r_eju_ .icon-shape p,#chatgpt-mermaid-_r_eju_ .image-shape p{background-color:rgb(252, 252, 252);padding:2px;}#chatgpt-mermaid-_r_eju_ .icon-shape .label rect,#chatgpt-mermaid-_r_eju_ .image-shape .label rect{opacity:0.5;background-color:rgb(252, 252, 252);fill:rgb(252, 252, 252);}#chatgpt-mermaid-_r_eju_ .label-icon{display:inline-block;height:1em;overflow:visible;vertical-align:-0.125em;}#chatgpt-mermaid-_r_eju_ .node .label-icon path{fill:currentColor;stroke:revert;stroke-width:revert;}#chatgpt-mermaid-_r_eju_ .node .neo-node{stroke:rgb(83, 154, 248);}#chatgpt-mermaid-_r_eju_ [data-look="neo"].node rect,#chatgpt-mermaid-_r_eju_ [data-look="neo"].cluster rect,#chatgpt-mermaid-_r_eju_ [data-look="neo"].node polygon{stroke:url(#chatgpt-mermaid-_r_eju_-gradient);filter:drop-shadow( 1px 2px 2px rgba(185,185,185,1));}#chatgpt-mermaid-_r_eju_ [data-look="neo"].swimlane.cluster rect{filter:none;}#chatgpt-mermaid-_r_eju_ [data-look="neo"].node path{stroke:url(#chatgpt-mermaid-_r_eju_-gradient);stroke-width:1px;}#chatgpt-mermaid-_r_eju_ [data-look="neo"].node .outer-path{filter:drop-shadow( 1px 2px 2px rgba(185,185,185,1));}#chatgpt-mermaid-_r_eju_ [data-look="neo"].node .neo-line path{stroke:rgb(83, 154, 248);filter:none;}#chatgpt-mermaid-_r_eju_ [data-look="neo"].node circle{stroke:url(#chatgpt-mermaid-_r_eju_-gradient);filter:drop-shadow( 1px 2px 2px rgba(185,185,185,1));}#chatgpt-mermaid-_r_eju_ [data-look="neo"].node circle .state-start{fill:#000000;}#chatgpt-mermaid-_r_eju_ [data-look="neo"].icon-shape .icon{fill:url(#chatgpt-mermaid-_r_eju_-gradient);filter:drop-shadow( 1px 2px 2px rgba(185,185,185,1));}#chatgpt-mermaid-_r_eju_ [data-look="neo"].icon-shape .icon-neo path{stroke:url(#chatgpt-mermaid-_r_eju_-gradient);filter:drop-shadow( 1px 2px 2px rgba(185,185,185,1));}#chatgpt-mermaid-_r_eju_ .node text{font-size:14px;font-weight:600;letter-spacing:normal;fill:rgb(0, 79, 153);}#chatgpt-mermaid-_r_eju_ .edgeLabels text{font-size:13px;font-weight:600;letter-spacing:-0.08px;fill:rgb(0, 79, 153);}#chatgpt-mermaid-_r_eju_ .node tspan[font-weight="normal"],#chatgpt-mermaid-_r_eju_ .edgeLabels tspan[font-weight="normal"]{font-weight:600;}#chatgpt-mermaid-_r_eju_ .edgeLabel .label rect{opacity:1;rx:13px;ry:13px;fill:rgb(245, 250, 255);stroke:rgb(206, 219, 229);stroke-width:1px;}#chatgpt-mermaid-_r_eju_ .node rect,#chatgpt-mermaid-_r_eju_ .node circle,#chatgpt-mermaid-_r_eju_ .node ellipse,#chatgpt-mermaid-_r_eju_ .node polygon,#chatgpt-mermaid-_r_eju_ .node path{fill:rgb(229, 243, 255);stroke:rgba(0, 0, 0, 0.1);stroke-width:1px;}#chatgpt-mermaid-_r_eju_ .node rect{rx:16px;ry:16px;}#chatgpt-mermaid-_r_eju_ .node.mermaid-decision .label-container{fill:rgb(245, 250, 255);stroke:rgb(206, 219, 229);stroke-dasharray:2px,2px;}#chatgpt-mermaid-_r_eju_ .edgePaths .flowchart-link{stroke:rgb(143, 143, 143);stroke-width:1px;stroke-linecap:round;stroke-linejoin:round;}#chatgpt-mermaid-_r_eju_ .marker{fill:rgb(143, 143, 143);stroke:rgb(143, 143, 143);}#chatgpt-mermaid-_r_eju_ :root{--mermaid-font-family:-apple-system-body,ui-sans-serif,-apple-system,system-ui,"Segoe UI","Helvetica","Apple Color Emoji","Arial",sans-serif,"Segoe UI Emoji","Segoe UI Symbol";}DeveloperGitGitHubGitHub ActionsDockerContainer RegistryHelmKubernetesPrometheusGrafanaGrafana AlloyLoki




Project Overview
This project demonstrates the implementation of a complete DevOps workflow for a containerized microservices application.
The platform covers:
- Source control with Git and GitHub
- Containerization with Docker
- Local development with Docker Compose
- Container image management
- Kubernetes orchestration
- Helm-based deployment
- GitHub Actions CI/CD
- Horizontal Pod Autoscaling
- Ingress-based routing
- Prometheus monitoring
- Grafana visualization
- Grafana Alloy log collection
- Loki log aggregation
- Kubernetes and application observability
Technology Stack
Category	Technology
Source Control	Git, GitHub
Containers	Docker
Local Development	Docker Compose
Container Registry	Docker Hub / Container Registry
Orchestration	Kubernetes
Local Kubernetes	Minikube
Package Management	Helm
CI/CD	GitHub Actions
Metrics	Prometheus
Visualization	Grafana
Kubernetes Metrics	Metrics Server
Kubernetes State	kube-state-metrics
Node Metrics	Node Exporter
Log Collection	Grafana Alloy
Log Storage	Loki
Scaling	Kubernetes HPA
Routing	Kubernetes Ingress


Application Structure
project/
├── services/
│   ├── auth-service/
│   ├── user-service/
│   ├── order-service/
│   └── payment-service/
│
├── frontend/
│
├── helm/
│   └── project/
│       ├── Chart.yaml
│       ├── values.yaml
│       └── templates/
│
├── monitoring/
├── logging/
│
├── .github/
│   └── workflows/
│       └── cicd.yml
│
├── docker-compose.yml
├── .gitignore
├── DEVOPS.md
└── README.md

DevOps Workflow
Developer
    │
    ▼
Git
    │
    ▼
GitHub
    │
    ▼
GitHub Actions
    │
    ├── Build
    ├── Test
    ├── Docker Build
    └── Docker Push
            │
            ▼
    Container Registry
            │
            ▼
          Helm
            │
            ▼
       Kubernetes
            │
     ┌──────┼─────────┐
     ▼      ▼         ▼
  Pods   Services   Ingress
            │
            ▼
           HPA
            │
     ┌──────┴──────┐
     ▼             ▼
Prometheus       Alloy
     │             │
     ▼             ▼
Grafana          Loki
                    │
                    ▼
                 Grafana

1. Source Control
Git is used to manage the application and DevOps configuration.
Developer
    ↓
Git
    ↓
GitHub

The repository contains application code, Docker configuration, Helm charts, monitoring configuration, logging configuration, and CI/CD workflows.
2. Containerization
Each microservice is packaged as a Docker image.
Microservice
     ↓
Dockerfile
     ↓
Docker Image
     ↓
Container Registry

This provides a consistent runtime environment across development and deployment environments.
3. Local Development
Docker Compose is used to run the application locally before deploying it to Kubernetes.
docker compose up
        ↓
Microservices
        ↓
Local Environment

4. Kubernetes
Kubernetes manages the application containers.
The deployment consists of:
- Deployments
- Pods
- Services
- ConfigMaps
- Secrets
- Ingress
- Horizontal Pod Autoscalers
Deployment
     ↓
ReplicaSet
     ↓
Pods

Services provide networking between the microservices.
Ingress provides external HTTP routing.
5. Helm
Helm packages the Kubernetes resources into a reusable chart.
Helm Chart
├── Chart.yaml
├── values.yaml
└── templates/

Instead of maintaining separate static Kubernetes manifests, deployment configuration is managed through Helm templates and values.
Example deployment flow:
helm lint ./helm/project
helm template project ./helm/project
helm install project ./helm/project
helm upgrade project ./helm/project

6. CI/CD
GitHub Actions automates the application delivery pipeline.
Git Push
   ↓
GitHub Actions
   ↓
Build
   ↓
Test
   ↓
Docker Build
   ↓
Push Image
   ↓
Helm Deployment
   ↓
Kubernetes

The goal is to eliminate repetitive manual deployment steps.
7. Autoscaling
Horizontal Pod Autoscaler automatically adjusts the number of Pods based on resource utilization.
Low CPU
   ↓
Fewer Pods

High CPU
   ↓
More Pods

Metrics Server provides CPU and memory metrics required for resource-based autoscaling.
8. Monitoring
Prometheus collects metrics from the Kubernetes environment.
Kubernetes
     ↓
Prometheus
     ↓
Grafana

The monitoring stack includes:
- Prometheus
- Grafana
- Metrics Server
- kube-state-metrics
- Node Exporter
Grafana is used to visualize application and Kubernetes metrics.
9. Logging
Application and Kubernetes logs are collected using Grafana Alloy and stored in Loki.
Pods
 ↓
Grafana Alloy
 ↓
Loki
 ↓
Grafana

Grafana provides centralized log querying and visualization.
Example LogQL:
{namespace="project", app=~"$service"}

10. Security & Configuration
Sensitive configuration is separated from application code.
ConfigMap
Used for non-sensitive configuration.
Secret
Used for:
- Database credentials
- Passwords
- API keys
- JWT secrets
- Other sensitive values
Sensitive information should never be committed to Git.
Application Configuration
        │
   ┌────┴────┐
   ▼         ▼
ConfigMap   Secret

GitHub Actions secrets are used for CI/CD credentials.
11. Deployment Verification
After deployment, the environment is verified at multiple levels.
Application
Services healthy
Pods running
Application accessible

Kubernetes
Deployments available
Services configured
Ingress routing correctly

Autoscaling
HPA active
Metrics available
Replica scaling functional

Observability
Prometheus collecting metrics
Grafana dashboards working
Alloy collecting logs
Loki storing logs

DevOps Documentation
Detailed implementation commands, troubleshooting procedures, deployment steps, port-forwarding commands, Helm commands, Kubernetes commands, monitoring commands, and logging commands are documented separately in:
DEVOPS.md
This keeps the main README focused on the architecture and project rather than becoming a command dump.
Final Architecture
                 ┌───────────────┐
                 │   Developer   │
                 └───────┬───────┘
                         │
                         ▼
                 ┌───────────────┐
                 │     GitHub    │
                 └───────┬───────┘
                         │
                         ▼
                 ┌───────────────┐
                 │ GitHub Actions│
                 └───────┬───────┘
                         │
                         ▼
                 ┌───────────────┐
                 │     Docker    │
                 └───────┬───────┘
                         │
                         ▼
                 ┌───────────────┐
                 │    Registry   │
                 └───────┬───────┘
                         │
                         ▼
                    ┌─────────┐
                    │  Helm   │
                    └────┬────┘
                         │
                         ▼
              ┌─────────────────────┐
              │     Kubernetes      │
              │                     │
              │ Deployments         │
              │ Services            │
              │ Pods                │
              │ HPA                 │
              │ Ingress             │
              └──────┬───────┬──────┘
                     │       │
             ┌───────┘       └────────┐
             ▼                        ▼
       ┌───────────┐            ┌───────────┐
       │ Prometheus│            │   Alloy    │
       └─────┬─────┘            └─────┬─────┘
             │                        │
             ▼                        ▼
       ┌───────────┐            ┌───────────┐
       │  Grafana  │◄───────────│    Loki   │
       └───────────┘            └───────────┘

Why this looks more professional
A recruiter opening the repository sees this order:
Project
   ↓
Architecture
   ↓
Technology Stack
   ↓
Application Structure
   ↓
DevOps Workflow
   ↓
Implementation
   ↓
Monitoring
   ↓
Logging
   ↓
Security
   ↓
Verification
   ↓
Detailed DEVOPS.md
