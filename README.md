# DevOps Project - Vamshidhar Reddy Neelipally
<img width="1447" height="736" alt="full-scale-project" src="https://github.com/user-attachments/assets/91e6e188-365f-45ed-bf0b-225554e2c197" />


End-to-end GitOps pipeline deploying a Dockerized Tomcat application
to Kubernetes on EKS using ArgoCD for automated sync.

## Project Flow
Developer pushes code to GitHub
         ↓
GitHub Repository (deployment.yaml, service.yaml)
         ↓
ArgoCD detects change automatically
         ↓
ArgoCD syncs to EKS cluster
         ↓
Kubernetes Deployment (2 replicas, tomcat namespace)
         ↓
LoadBalancer Service
         ↓
Live Application (Tomcat + custom index.html)

## Projects

### 🐳 docker-tomcat
Custom Dockerized Tomcat application built from scratch.
- Built custom Docker image with application files baked in
- Configured role-based Tomcat manager access
- Tagged and pushed to DockerHub (vamshi82/my-tomcat:latest)
- Deployed on AWS EC2

### ☸️ deploymentfiles
Kubernetes manifests for deploying the Tomcat app to EKS.
- Deployment with 2 replicas and rolling update strategy
- LoadBalancer Service exposing the app externally
- Rolling updates and rollback using kubectl rollout

### 🔄 argocd
GitOps continuous deployment using ArgoCD.
- Connected to this GitHub repository
- Auto-syncs cluster when manifests change in deploymentfiles/
- Visual dashboard showing deployment health and sync status

## Tech Stack
Docker • Kubernetes • EKS • ArgoCD • AWS • Git • Linux

## Author
**Vamshidhar Reddy Neelipally**
AWS Certified Cloud Practitioner
[LinkedIn](https://www.linkedin.com/in/n-vamshidhar-reddy/) • [DockerHub](https://hub.docker.com/u/vamshi82)
