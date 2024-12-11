### Example Voting App - CI/CD Pipeline

This project demonstrates a complete CI/CD pipeline setup for the Example Voting App. The implementation showcases my DevOps expertise, including:
- CI/CD with GitLab
- Docker and Kubernetes
- GitOps with ArgoCD
- Infrastructure as Code (IaC) using Terraform

## Overview
The pipeline automates the following:

# Continuous Integration:
- Builds Docker images for microservices (vote, result, worker).
- Pushes images to Docker Hub.

# Continuous Delivery:
- Updates Kubernetes manifests with new image tags.
- Deploys updates to an Amazon EKS cluster via ArgoCD.
