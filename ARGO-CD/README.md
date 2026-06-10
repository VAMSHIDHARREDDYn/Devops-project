# ArgoCD - GitOps Deployment

ArgoCD installed on EKS cluster, configured to automatically sync
Kubernetes manifests from this GitHub repository to the cluster.

## What is GitOps
GitOps means your Git repository is the single source of truth for
your infrastructure. ArgoCD watches the repository and automatically
syncs the cluster to match whatever is in Git.

## What This Does
- Watches the `deploymentfiles/` folder in this repository
- Automatically deploys changes to EKS when code is pushed to GitHub
- Provides visual dashboard showing deployment health and sync status
- No manual kubectl apply needed after initial setup

## ArgoCD Setup Commands
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
kubectl patch svc argocd-server -n argocd -p '{"spec": {"type": "LoadBalancer"}}'

## Application Configuration
- App Name: tomcat
- Namespace: tomcat
- Source Repository: https://github.com/VAMSHIDHARREDDYn/Devops-project
- Source Path: deploymentfiles/
- Sync Policy: Automatic
- Health Status: Healthy

## How GitOps Works in This Project
1. Update deployment.yaml or service.yaml in deploymentfiles/
2. Push changes to GitHub
3. ArgoCD detects the change automatically
4. ArgoCD syncs cluster to match new state
5. Application updates with zero manual intervention

## Screenshots
![ArgoCD Login](screenshots/argocd.png)
![ArgoCD Dashboard](screenshots/argocd-1.png)
![App Tree](screenshots/argo-cd-3.png)
![Deployment Details](screenshots/argocd-4.png)
![Service Details](screenshots/argocd-5.png)
![Live Application](screenshots/argocd-6.png)

## Tech Stack
ArgoCD • Kubernetes • EKS • GitOps • GitHub • AWS
