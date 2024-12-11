# Example Voting App - CI/CD Pipeline

This project demonstrates a complete CI/CD pipeline setup for the Example Voting App. The implementation showcases my DevOps expertise, including:
- CI/CD with GitLab
- Docker and Kubernetes
- GitOps with ArgoCD
- Infrastructure as Code (IaC) using Terraform

## How It Works

![Uploading diagram-export-12-11-2024-1_44_49-PM.png…]()

### Continuous Integration:

1. Developer pushes code changes to the repository.
2. GitLab CI/CD pipeline is triggered, with the following stages:
   - Build and Push: Builds Docker images for microservices.
   - Update Deployment: Updates Kubernetes manifests with new image tags.
### Continuous Delivery:
- Deploys updates to an Amazon EKS cluster via ArgoCD.
  
## Architecture

![Architecture diagram](architecture.excalidraw.png)

* A front-end web app in [Python](/vote) which lets you vote between two options
* A [Redis](https://hub.docker.com/_/redis/) which collects new votes
* A [.NET](/worker/) worker which consumes votes and stores them in…
* A [Postgres](https://hub.docker.com/_/postgres/) database backed by a Docker volume
* A [Node.js](/result) web app which shows the results of the voting in real time

## Notes

The voting application only accepts one vote per client browser. It does not register additional votes if a vote has already been submitted from a client.

This isn't an example of a properly architected perfectly designed distributed app... it's just a simple
example of the various types of pieces and languages you might see (queues, persistent data, etc), and how to
deal with them in Docker at a basic level.
