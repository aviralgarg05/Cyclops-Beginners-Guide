# MyApp Deployment with Cyclops

## Overview

This repository contains the configurations and scripts to deploy MyApp using Cyclops and Kubernetes.

## Getting Started

### Prerequisites

- Docker
- Kubernetes (Minikube or any other Kubernetes cluster)
- Helm (optional, for Helm chart users)

### Build and Push Docker Image

1. Build the Docker image:
    ```bash
    docker build -t myapp:latest .
    ```

2. Push the image to Docker Hub:
    ```bash
    docker tag myapp:latest <your-dockerhub-username>/myapp:latest
    docker push <your-dockerhub-username>/myapp:latest
    ```

### Deploying to Kubernetes

1. Apply the deployment configuration:
    ```bash
    kubectl apply -f deployment.yaml
    ```

2. Apply the service configuration:
    ```bash
    kubectl apply -f service.yaml
    ```

### Using Helm (Optional)

1. Install Helm:
    ```bash
    # Follow Helm installation instructions from https://helm.sh/docs/intro/install/
    ```

2. Deploy using Helm:
    ```bash
    helm install myapp ./charts/myapp
    ```

### Access the Application

Use port-forwarding to access the application:
```bash
kubectl port-forward svc/myapp-service 8881:80

Navigate to http://localhost:8881 to see the application running.

### Contributing
Feel free to submit pull requests or issues if you have any improvements or questions.

### License
This project is licensed under the MIT License.

``` bash
Make sure to replace placeholders like `<your-dockerhub-username>` with your actual Docker Hub username or any other relevant information. This setup will help you manage your Kubernetes deployments and containerized applications effectively with Cyclops.
```