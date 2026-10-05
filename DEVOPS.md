# 🚀 SKY-DASH — Complete DevOps Implementation

## 1. Project Overview

SKY-DASH is a Food Delivery Microservices application used as a hands-on DevOps practice project.

The application contains multiple microservices and was containerized, deployed to Kubernetes, packaged with Helm, automated using GitHub Actions, monitored using Prometheus/Grafana, and integrated with centralized logging using Loki/Grafana Alloy.

### Microservices

- Auth Service
- Restaurant Service
- Delivery Service
- Payment Service
- Order Service
- Frontend Service
- Delivery Frontend Service

---

# 2. DevOps Architecture

```text
                         Developer
                             |
                             | git push
                             v
                    +----------------+
                    |     GitHub     |
                    +-------+--------+
                            |
                            v
                   +-------------------+
                   |  GitHub Actions   |
                   |      CI/CD        |
                   +---------+---------+
                             |
                             v
                     Docker Build
                             |
                             v
                     +---------------+
                     |   Docker Hub  |
                     +-------+-------+
                             |
                             | Pull Image
                             v
                  +----------------------+
                  |     Kubernetes      |
                  |       Minikube      |
                  +----------+-----------+
                             |
          +------------------+------------------+
          |                  |                  |
          v                  v                  v
     Deployments          Services             HPA
          |
          v
        Pods
          |
          +-------------------------+
          |                         |
          v                         v
     Prometheus                  Alloy
          |                         |
          v                         v
      Grafana                    Loki
          |                         |
          +-----------+-------------+
                      |
                      v
                   Grafana

3. Complete DevOps Workflow
Developer
   ↓
Write / Modify Code
   ↓
Git
   ↓
GitHub
   ↓
GitHub Actions
   ↓
Detect Changed Service
   ↓
Docker Build
   ↓
Docker Image
   ↓
Docker Hub
   ↓
Helm
   ↓
Kubernetes
   ↓
Application Pods
   ↓
HPA / Ingress
   ↓
Prometheus → Grafana
   ↓
Alloy → Loki → Grafana

4. Technology Stack
Technology	Purpose
Git	Version control
GitHub	Source-code repository
Docker	Containerization
Docker Hub	Container image registry
Kubernetes	Container orchestration
Minikube	Local Kubernetes cluster
Helm	Kubernetes package management
GitHub Actions	CI/CD automation
Self-hosted Runner	Executes CI/CD jobs
Prometheus	Metrics collection
Grafana	Monitoring and visualization
kube-state-metrics	Kubernetes object-state metrics
Node Exporter	Node-level metrics
Metrics Server	CPU/memory metrics for HPA
Loki	Log aggregation
Grafana Alloy	Kubernetes log collection
HPA	Automatic Pod scaling
Ingress	HTTP routing


5. Project Structure
Food-Delivery-Microservices/
│
├── frontend/
├── backend/
│
├── helm/
│   └── skydash/
│       ├── Chart.yaml
│       ├── values.yaml
│       ├── secrets-values.yaml
│       └── templates/
│
├── .github/
│   └── workflows/
│       └── cicd.yml
│
├── .gitignore
└── README.md

The DevOps documentation is maintained separately in:
DEVOPS.md

6. Git
Purpose
Git is used for version control and maintaining the project history.
Basic workflow
Working Directory
       ↓
git add
       ↓
git commit
       ↓
git push
       ↓
GitHub

Important commands
git status

Check modified and untracked files.
git add .

Stage changes.
git commit -m "commit message"

Create a commit.
git push origin main

Push changes to GitHub.
git pull origin main

Pull the latest changes.
git log --oneline

View commit history.
7. GitHub
Purpose
GitHub stores the source code and acts as the trigger point for CI/CD.
Repository:
Food-Delivery-Microservices

The main deployment branch is:
main

GitHub also provides:
- Repository hosting
- Branch management
- Pull Requests
- GitHub Actions
- GitHub Secrets
8. Docker
Purpose
Docker packages each application service and its dependencies into a container image.
Docker workflow
Application
    ↓
Dockerfile
    ↓
docker build
    ↓
Docker Image
    ↓
docker run
    ↓
Container

Check Docker
docker --version

Build image
docker build -t <image-name>:<tag> .

Example:
docker build -t auth-service:v1 .

List images
docker images

Run container
docker run -d -p 5001:5001 <image-name>:<tag>

Check containers
docker ps

Check all containers
docker ps -a

Stop container
docker stop <container-id>

Remove container
docker rm <container-id>

Remove unused images
docker image prune -a

9. Docker Hub
Purpose
Docker Hub is used as the container image registry.
The SKY-DASH images are stored in Docker Hub.
Repositories include:
chirudevops46/auth-service
chirudevops46/restaurant-service
chirudevops46/delivery-service
chirudevops46/payment-service
chirudevops46/order-service
chirudevops46/frontend-service
chirudevops46/delivery-frontend-service

Login
docker login

Tag image
docker tag <local-image> <username>/<repository>:<tag>

Push image
docker push <username>/<repository>:<tag>

Pull image
docker pull <username>/<repository>:<tag>

10. Kubernetes
Purpose
Kubernetes runs and manages the Docker containers.
The local Kubernetes environment used for SKY-DASH is Minikube.
The application namespace is:
skydash

Check cluster
kubectl cluster-info

Check nodes
kubectl get nodes

Create namespace
kubectl create namespace skydash

Check namespace
kubectl get ns

11. Kubernetes Deployment
A Deployment manages application Pods.
Deployment
    ↓
ReplicaSet
    ↓
Pods
    ↓
Containers

View deployments
kubectl get deployments -n skydash

Describe deployment
kubectl describe deployment <deployment-name> -n skydash

View Pods
kubectl get pods -n skydash

Detailed Pod information
kubectl describe pod <pod-name> -n skydash

Pod logs
kubectl logs <pod-name> -n skydash

Follow logs
kubectl logs -f <pod-name> -n skydash

12. Kubernetes Services
Services provide stable networking for Pods.
             Service
                |
       +--------+--------+
       |        |        |
       v        v        v
      Pod      Pod      Pod

View Services
kubectl get svc -n skydash

Describe Service
kubectl describe svc <service-name> -n skydash

SKY-DASH Services
auth-service
restaurant-service
delivery-service
payment-service
order-service
frontend-service
delivery-frontend-service

13. ConfigMaps
ConfigMaps store non-sensitive configuration.
View ConfigMaps
kubectl get configmaps -n skydash

Describe ConfigMap
kubectl describe configmap <configmap-name> -n skydash

14. Kubernetes Secrets
Secrets store sensitive configuration such as:
- Database credentials
- JWT secrets
- API tokens
- Authentication values
View Secrets
kubectl get secrets -n skydash

Describe Secret
kubectl describe secret <secret-name> -n skydash

Sensitive values should never be committed directly to GitHub.
15. Minikube
Purpose
Minikube provides the local Kubernetes cluster used for development and testing.
Start Minikube
minikube start

Check status
minikube status

Get cluster IP
minikube ip

Enable Ingress
minikube addons enable ingress

Check addons
minikube addons list

Open Kubernetes service
minikube service <service-name> -n skydash

SSH into Minikube
minikube ssh

16. Helm
Purpose
Helm is used to package, configure, install, and upgrade the Kubernetes application.
Helm chart:
helm/skydash/
├── Chart.yaml
├── values.yaml
└── templates/

Check Helm
helm version

Lint chart
helm lint ./helm/skydash

Render templates
helm template skydash ./helm/skydash

Install
helm install skydash ./helm/skydash -n skydash

List releases
helm list -n skydash

Upgrade
helm upgrade skydash ./helm/skydash -n skydash

Check release status
helm status skydash -n skydash

View release history
helm history skydash -n skydash

Rollback
helm rollback skydash <revision> -n skydash

17. Helm Values
values.yaml contains configurable values such as:
- Service names
- Docker image repositories
- Image tags
- Replica counts
- Service ports
- ConfigMap names
- Secret names
- HPA configuration
Example:
services:
  order:
    name: order-service
    image:
      repository: <docker-repository>
      tag: latest
    replicas: 1
    port: 5005

Helm templates use these values to generate Kubernetes manifests.
18. GitHub Actions CI/CD
Purpose
GitHub Actions automates the application build and deployment process.
Workflow
git push
   ↓
GitHub
   ↓
GitHub Actions
   ↓
Detect Changed Service
   ↓
Docker Build
   ↓
Docker Push
   ↓
Helm Upgrade
   ↓
Kubernetes
   ↓
Rollout Verification

The workflow is located at:
.github/workflows/cicd.yml

CI/CD responsibilities
1. Detect changed services
2. Checkout source code
3. Login to Docker Hub
4. Build Docker image
5. Tag image using GitHub commit SHA
6. Push image to Docker Hub
7. Create temporary Helm secret configuration
8. Upgrade the Kubernetes deployment using Helm
9. Wait for Kubernetes rollout
19. GitHub Actions Self-Hosted Runner
A self-hosted GitHub Actions runner was used to execute the CI/CD workflow.
Runner location on Windows:
C:\Windows\System32\actions-runner

Start runner
Open PowerShell:
cd C:\Windows\System32\actions-runner

Then:
.\run.cmd

Expected state:
Connected to GitHub
Listening for Jobs

The runner provides the environment required to build Docker images and interact with the local Kubernetes/Minikube environment.
20. CI/CD Image Versioning
The CI/CD workflow uses the GitHub commit SHA as the Docker image tag.
Concept:
Git Commit
     ↓
GitHub SHA
     ↓
Docker Image Tag
     ↓
Docker Hub
     ↓
Kubernetes

This makes it possible to identify which source-code commit produced a deployed image.
21. Prometheus
Purpose
Prometheus collects and stores time-series metrics.
The monitoring stack is installed in:
monitoring

namespace.
Check monitoring Pods
kubectl get pods -n monitoring

Check Services
kubectl get svc -n monitoring

Prometheus monitors Kubernetes and infrastructure metrics.
Examples:
- CPU
- Memory
- Pod status
- Pod restarts
- Deployment state
- HPA state
22. kube-state-metrics
kube-state-metrics exposes metrics about Kubernetes object state.
It provides information about:
- Pods
- Deployments
- ReplicaSets
- Services
- HPA
- Nodes
- Jobs
- Other Kubernetes resources
Example:
Kubernetes API
      ↓
kube-state-metrics
      ↓
Prometheus
      ↓
Grafana

23. Node Exporter
Node Exporter provides system-level metrics from Kubernetes nodes.
Examples:
- CPU
- Memory
- Filesystem
- System resource information
Workflow:
Kubernetes Node
      ↓
Node Exporter
      ↓
Prometheus
      ↓
Grafana

24. Metrics Server
Metrics Server provides CPU and memory resource metrics to Kubernetes.
It is particularly important for HPA.
Check Metrics Server
kubectl get pods -n kube-system | grep metrics

Check resource metrics
kubectl top pods -n skydash

kubectl top nodes

25. Grafana
Purpose
Grafana is used to visualize metrics and logs.
Grafana is connected to:
Prometheus → Metrics
Loki → Logs

Port-forward Grafana
kubectl port-forward -n monitoring svc/monitoring-grafana 3000:80

Then open:
http://localhost:3000

The SKY-DASH monitoring dashboard contains:
- CPU usage by Pod
- Memory usage by Pod
- HPA current replicas
- HPA desired replicas
- HPA replica history
- Pod restarts
- Pod status
- Deployment availability
- Pod count
- Deployment count
- Running Pod count
26. Prometheus Alerts
Alerts were configured for important conditions.
Pod Not Running
Detects Pods that are not in the Running state.
High CPU Usage
Detects high CPU usage by SKY-DASH Pods.
Alerts are evaluated by the Prometheus/Grafana monitoring stack.
27. Loki
Purpose
Loki is used for centralized log aggregation.
Prometheus handles metrics:
Prometheus → Metrics

Loki handles logs:
Loki → Logs

Loki was installed in:
loki

namespace.
Check Loki
kubectl get pods -n loki

Check Loki Services
kubectl get svc -n loki

28. Grafana Alloy
Purpose
Grafana Alloy collects Kubernetes container logs and forwards them to Loki.
Workflow:
Kubernetes Pods
      ↓
Container Logs
      ↓
Grafana Alloy
      ↓
Loki
      ↓
Grafana

Alloy discovers Kubernetes Pods and adds labels such as:
namespace
pod
container
app

29. Loki + Alloy Configuration
Alloy is configured to discover Kubernetes Pods and forward logs to Loki.
Loki endpoint used inside Kubernetes:
http://loki.loki.svc.cluster.local:3100/loki/api/v1/push

Check Alloy
kubectl get pods -n loki

Check Alloy logs
kubectl logs -n loki <alloy-pod>

30. Grafana Loki Queries
View all SKY-DASH logs:
{namespace="skydash"}

Filter logs by service:
{namespace="skydash", app=~"$query"}

Filter error logs:
{namespace="skydash", app=~"$query"} |= "error"

Loki labels include:
namespace
pod
container
app
service_name
instance
job

31. HPA — Horizontal Pod Autoscaler
HPA automatically adjusts the number of Pods according to resource utilization.
HPA was configured for:
Order Service
Restaurant Service

Configuration:
Minimum Replicas = 2
Maximum Replicas = 5
CPU Target       = 70%

Workflow:
High CPU
   ↓
Metrics Server
   ↓
HPA
   ↓
Increase Replicas

When CPU decreases:
Low CPU
   ↓
HPA
   ↓
Decrease Replicas

Check HPA
kubectl get hpa -n skydash

Describe HPA
kubectl describe hpa <hpa-name> -n skydash

Watch HPA
kubectl get hpa -n skydash -w

32. HPA Testing
CPU load was generated to verify Kubernetes autoscaling.
The expected workflow:
CPU Load
   ↓
CPU Utilization Increases
   ↓
Metrics Server
   ↓
HPA Detects Utilization
   ↓
Desired Replicas Increase
   ↓
Kubernetes Creates Pods

When the load stops:
CPU Utilization Decreases
   ↓
HPA
   ↓
Replicas Scale Down

33. Ingress
Ingress provides HTTP routing into the Kubernetes application.
Workflow:
Browser
   ↓
Ingress
   ↓
Kubernetes Service
   ↓
Application Pod

Minikube Ingress addon:
minikube addons enable ingress

Check Ingress:
kubectl get ingress -n skydash

Describe Ingress:
kubectl describe ingress -n skydash

34. Application Health and Troubleshooting
Important Kubernetes commands used during troubleshooting:
Check everything
kubectl get all -n skydash

Check Pods
kubectl get pods -n skydash

Watch Pods
kubectl get pods -n skydash -w

Check Pod details
kubectl describe pod <pod-name> -n skydash

Check previous crashed container logs
kubectl logs <pod-name> -n skydash --previous

Check deployment
kubectl describe deployment <deployment-name> -n skydash

Check events
kubectl get events -n skydash --sort-by=.lastTimestamp

Check rollout
kubectl rollout status deployment/<deployment-name> -n skydash

Check rollout history
kubectl rollout history deployment/<deployment-name> -n skydash

35. Common Kubernetes Problems Encountered
During implementation, several practical DevOps issues were encountered and investigated.
ImagePullBackOff
Usually indicates that Kubernetes cannot pull the required image.
Investigation:
kubectl describe pod <pod-name> -n skydash

CrashLoopBackOff
Indicates that a container repeatedly starts and crashes.
Investigation:
kubectl logs <pod-name> -n skydash

and:
kubectl logs <pod-name> -n skydash --previous

Helm Conflicts
Helm upgrades can fail when Kubernetes resources already exist with conflicting ownership or field management.
Investigation:
helm status skydash -n skydash

kubectl describe deployment <deployment-name> -n skydash

Docker Disk Space
Multiple Docker images, containers, and Kubernetes resources can consume significant disk space.
Useful command:
docker system df

Cleanup:
docker image prune -a

36. Useful Monitoring Commands
Prometheus Pods
kubectl get pods -n monitoring

Grafana Pods
kubectl get pods -n monitoring

Loki Pods
kubectl get pods -n loki

Alloy Pods
kubectl get pods -n loki

Kubernetes metrics
kubectl top pods -n skydash

kubectl top nodes

37. Final Verification
Before considering the deployment healthy, verify:
Kubernetes
kubectl get pods -n skydash

kubectl get deployments -n skydash

kubectl get svc -n skydash

kubectl get hpa -n skydash

kubectl get ingress -n skydash

Helm
helm list -n skydash

helm status skydash -n skydash

Monitoring
kubectl get pods -n monitoring

Logging
kubectl get pods -n loki

CI/CD
Verify the GitHub Actions workflow completed successfully and the Kubernetes rollout completed successfully.
38. Complete Tool Relationship
Each tool has a specific responsibility:
Git
 ↓
Tracks Code

GitHub
 ↓
Stores Code

GitHub Actions
 ↓
Automates CI/CD

Docker
 ↓
Builds Application Images

Docker Hub
 ↓
Stores Application Images

Kubernetes
 ↓
Runs Application Containers

Helm
 ↓
Manages Kubernetes Deployment

HPA
 ↓
Scales Application Pods

Prometheus
 ↓
Collects Metrics

kube-state-metrics
 ↓
Provides Kubernetes Object Metrics

Node Exporter
 ↓
Provides Node Metrics

Metrics Server
 ↓
Provides Resource Metrics for HPA

Grafana
 ↓
Visualizes Metrics + Logs

Alloy
 ↓
Collects Kubernetes Logs

Loki
 ↓
Stores and Queries Logs

Ingress
 ↓
Routes External Traffic

39. Final DevOps Workflow
                    DEVELOPER
                        |
                        v
                       GIT
                        |
                        v
                     GITHUB
                        |
                        v
                GITHUB ACTIONS
                        |
                 +------+------+
                 |             |
                 v             v
             BUILD/TEST    DOCKER BUILD
                               |
                               v
                          DOCKER HUB
                               |
                               v
                             HELM
                               |
                               v
                         KUBERNETES
                               |
             +-----------------+-----------------+
             |                 |                 |
             v                 v                 v
          SERVICES        DEPLOYMENTS           HPA
                               |
                               v
                              PODS
                               |
                 +-------------+-------------+
                 |                           |
                 v                           v
            PROMETHEUS                    ALLOY
                 |                           |
                 v                           v
              GRAFANA                      LOKI
                 ^                           |
                 |                           |
                 +---------------------------+

40. Project Outcome
Through this project, the complete DevOps lifecycle was implemented and practiced:
Source Code
    ↓
Version Control
    ↓
Containerization
    ↓
Container Registry
    ↓
Kubernetes Deployment
    ↓
Helm
    ↓
CI/CD
    ↓
Autoscaling
    ↓
Monitoring
    ↓
Centralized Logging

The project provided hands-on experience with Docker, Kubernetes, Helm, GitHub Actions, Prometheus, Grafana, Loki, Alloy, HPA, Ingress, and Kubernetes troubleshooting.
👨‍💻 Author
Chiranjeevi Pasupuleti
Aspiring DevOps Engineer

**Now you only need one action:** create `DEVOPS.md`, paste the **entire block above**, save it, and push it:

```bash
cd /d/Devops/SKY-DASH/Food-Delivery-Microservices

touch DEVOPS.md

code DEVOPS.md

Paste → Ctrl+S, then:
git add DEVOPS.md
git commit -m "docs: add complete DevOps documentation"
git push origin main