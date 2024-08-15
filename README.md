## Overview

This repository showcases a robust Continuous Integration and Continuous Deployment (CI/CD) pipeline, leveraging a popular DevOps toolset with a strong emphasis on GitOps practices. The technology stack features AKS, Kubernetes (K8s), Kustomize, ArgoCD, Jenkins, Gradle, Docker, and DockerHub

## Codebase Structure

/springboot-demo-app: Contains the source code of the application.
/gitops-demo: Includes Kubernetes deployment manifest files based on Kustomized.

## ⚠️ Note on Repository Structure

Though GitOps best practices typically advocate for maintaining separate repositories for code and manifests, this project intentionally combines them into a single repository. This approach aims to streamline the learning curve for beginners and emphasize the critical role Argo CD plays in the continuous deployment process.

## CI/CD Flow

1. Developers push their code to the GitHub repository.
2. A Jenkins CI/CD pipeline is automatically triggered via a GitHub webhook.
3. Gradle is used to download dependencies, build the application, and create artifacts.
4. The application is containerized with Docker, and a Docker image is generated.
5. The Docker image is pushed to DockerHub, ensuring it is available and versioned.
6. During the Test Deployment stage, the image version in the Infra/GitOps repository (in this case, the same repository) is updated.
7. ArgoCD, the continuous deployment tool, continuously monitors changes in a specific path of the Infra repository and orchestrates updates to the Kubernetes deployment based on the new image.
