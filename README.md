# 🚀 Brain Tasks Application - CI/CD Deployment using AWS EKS

## 📌 Project Overview

This project demonstrates a complete DevOps CI/CD pipeline for deploying the **Brain Tasks Application** on **Amazon EKS (Elastic Kubernetes Service)**. The application is containerized using Docker, stored in Docker Hub, and automatically deployed to Kubernetes through AWS CodePipeline and CodeBuild.

The project showcases industry-standard DevOps practices including containerization, Kubernetes orchestration, automated CI/CD, and cloud deployment.

---

## 🛠️ Technologies Used

- Git & GitHub
- Docker
- Docker Hub
- AWS EKS (Elastic Kubernetes Service)
- Kubernetes
- AWS CodeBuild
- AWS CodePipeline
- AWS CloudWatch
- AWS IAM
- AWS CLI
- kubectl

---

## 📂 Project Structure

```
Brain-Tasks-App/
│
├── dist/
│   ├── assets/
│   ├── index.html
│   └── vite.svg
│
├── k8s/
│   ├── deployment.yaml
│   └── service.yaml
│
├── Dockerfile
├── buildspec.yml
├── README.md
└── .gitignore
```

---

# 🏗️ Architecture

```
                GitHub Repository
                       │
                       ▼
               AWS CodePipeline
                       │
                       ▼
               AWS CodeBuild
                       │
             Build Docker Image
                       │
                       ▼
                 Docker Hub
                       │
                       ▼
                 Amazon EKS
                       │
                Kubernetes Cluster
                       │
         Deployment + Service YAML
                       │
                       ▼
           Kubernetes LoadBalancer
                       │
                       ▼
              Brain Tasks Application
```

---

# ⚙️ Prerequisites

Before starting, ensure the following tools are installed:

- Git
- Docker Desktop
- AWS CLI
- kubectl
- eksctl
- AWS Account
- Docker Hub Account

---

# 🚀 Setup Instructions

## 1. Clone Repository

```bash
git clone https://github.com/YOUR_USERNAME/Brain-Task-app.git

cd Brain-Task-app
```

---

## 2. Build Docker Image

```bash
docker build -t brain-tasks-app:v1 .
```

---

## 3. Run Docker Container

```bash
docker run -d -p 3000:80 brain-tasks-app:v1
```

---

## 4. Push Docker Image to Docker Hub

```bash
docker login

docker tag brain-tasks-app:v1 YOUR_DOCKERHUB_USERNAME/brain-tasks-app:v1

docker push YOUR_DOCKERHUB_USERNAME/brain-tasks-app:v1
```

---

## 5. Create Amazon EKS Cluster

```bash
eksctl create cluster \
--name brain-tasks-cluster \
--region ap-south-1 \
--nodes 2
```

---

## 6. Verify Cluster

```bash
kubectl get nodes
```

---

## 7. Deploy Kubernetes Resources

```bash
kubectl apply -f k8s/deployment.yaml

kubectl apply -f k8s/service.yaml
```

---

## 8. Verify Deployment

```bash
kubectl get deployment

kubectl get pods

kubectl get svc
```

---

# 🔄 CI/CD Pipeline Workflow

1. Developer pushes code to GitHub.
2. AWS CodePipeline detects the new commit.
3. AWS CodeBuild builds the Docker image.
4. Docker image is pushed to Docker Hub.
5. CodePipeline deploys Kubernetes manifests to Amazon EKS.
6. Kubernetes updates the running application.
7. Application becomes available through the LoadBalancer.

---

# ☁️ AWS Services Used

- Amazon EKS
- AWS CodePipeline
- AWS CodeBuild
- AWS IAM
- AWS CloudWatch
- Elastic Load Balancer (ELB)

---

# 📊 Monitoring

- Build logs are monitored using AWS CodeBuild and CloudWatch.
- Deployment status is monitored through AWS CodePipeline.
- Kubernetes resources are monitored using kubectl commands.

Useful commands:

```bash
kubectl get nodes

kubectl get deployment

kubectl get pods

kubectl get svc

kubectl logs <pod-name>
```

---

# 🌐 Application URL

```
Paste your Kubernetes LoadBalancer URL here
```

Example:

```
http://xxxxxxxxxxxxxxxx.ap-south-1.elb.amazonaws.com
```

---

# 🔖 LoadBalancer ARN

```
Paste your LoadBalancer ARN here
```

Example:

```
arn:aws:elasticloadbalancing:ap-south-1:ACCOUNT-ID:loadbalancer/net/xxxxxxxxxxxxxxxx
```

---

# 📸 Screenshots

Include screenshots of:

- GitHub Repository
- Docker Hub Repository
- Docker Image Build
- Amazon EKS Cluster
- kubectl get nodes
- kubectl get pods
- kubectl get svc
- Running Application
- AWS CodeBuild Success
- AWS CodePipeline Success
- CloudWatch Logs

---

# 📚 Learning Outcomes

Through this project, I gained hands-on experience with:

- Docker containerization
- Kubernetes deployments
- Amazon EKS
- CI/CD using AWS CodePipeline
- AWS CodeBuild automation
- Kubernetes Services and Deployments
- Docker Hub image management
- Cloud-based application deployment

---

# 👨‍💻 Author

**Vinay K**

GitHub: https://github.com/VINAY8855
