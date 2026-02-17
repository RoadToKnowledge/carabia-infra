# Carabia Infra Repository

This repository contains Kubernetes and ArgoCD deployment files
for the Carabia .NET 8 Razor application.

## Structure

kubernetes/  -> Deployment YAMLs  
argocd/      -> ArgoCD Application  
ecs/         -> ECS Task Definition  

## Deployment Steps

1. Build Docker Image via GitHub Actions
2. Push Image to Amazon ECR
3. ArgoCD detects change
4. EKS auto deploys pods
5. RDS used as database

## Commands

Update kubeconfig:
aws eks --region ap-south-1 update-kubeconfig --name carabia-eks

Apply ArgoCD:
kubectl apply -f argocd/application.yaml
