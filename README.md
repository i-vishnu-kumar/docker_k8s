
# 📦 Python App in Docker + Kubernetes

This project demonstrates how to containerize a Python app using Docker and deploy it on Kubernetes using a Deployment and Service.

## 🧠 Prerequisites

- Docker installed  
- Kubernetes cluster (local or cloud like GKE, EKS, etc.)  
- `kubectl` configured  
- Docker Hub account (or any image registry)

## 🐳 Docker Instructions

### 1. Build the Docker image

```bash
docker build -t your-dockerhub-username/your-image-name:tag .

2. Push the image to Docker Hub

docker push your-dockerhub-username/your-image-name:tag

Make sure to replace your-dockerhub-username/your-image-name:tag with your actual image details.

⸻

☸️ Kubernetes Deployment

1. Apply the Kubernetes configuration

kubectl apply -f kube-setup.yaml

2. Check the deployed pods

kubectl get pods

3. Get external IP (for LoadBalancer service)

kubectl get svc my-python-app-service

Once the external IP is available, access your app using:

curl http://<external-ip>


⸻

✅ Notes
	•	This app listens on port 80 inside the container.
	•	The environment variable NAME is set to World and can be accessed inside the Python code using os.environ['NAME'].
	•	The Kubernetes Deployment creates 3 replicas of the app and uses a LoadBalancer service to expose it.
	•	If using a local cluster (e.g. Minikube), replace LoadBalancer with NodePort or use minikube tunnel to access the service.

