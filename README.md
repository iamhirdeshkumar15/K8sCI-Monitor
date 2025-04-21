# 🚀 K8SCI-Monitor – CI/CD Pipeline with Kubernetes Monitoring

This project demonstrates an end-to-end DevOps pipeline that deploys a static portfolio website using Jenkins, Docker, Kubernetes, and real-time monitoring with Prometheus and Grafana.

## 📌 Project Summary

- Automates code build, test, and deployment using Jenkins CI/CD
- Containerizes the application using Docker and hosts the image on DockerHub
- Deploys the container on a Kubernetes cluster with Service and Ingress
- Collects system and pod metrics using Prometheus
- Visualizes real-time metrics using Grafana dashboards
- Provides a web-based Kubernetes Dashboard for managing cluster resources

## 🧰 Tech Stack

| Tool                  | Purpose                              |
|-----------------------|--------------------------------------|
| GitHub                | Source code repository               |
| Jenkins               | CI/CD automation                     |
| Docker & DockerHub    | Containerization & image hosting     |
| Kubernetes            | Application deployment               |
| Kubernetes Dashboard  | Cluster visibility & resource management |
| Prometheus            | Monitoring cluster & pods            |
| Grafana               | Metrics visualization                |

## 🛠️ Workflow

1. Developer pushes code to GitHub
2. Jenkins is triggered via webhook
3. Jenkins builds Docker image and pushes it to DockerHub
4. Kubernetes pulls the image and deploys it via YAML manifests
5. Prometheus scrapes metrics from cluster components
6. Grafana displays dashboards for CPU, memory, pod health, etc.
7. Kubernetes Dashboard provides a GUI to monitor and interact with all cluster resources

## 🔍 Monitoring Stack

- Prometheus Operator (via kube-prometheus-stack)
- kube-state-metrics and node-exporter
- Grafana with Kubernetes dashboards
- Kubernetes Dashboard (via kubectl proxy or NodePort)

## 📊 Sample Prometheus Queries

```promql
100 - (avg by (instance) (rate(node_cpu_seconds_total{mode="idle"}[5m])) * 100)
100 * (1 - (node_memory_MemAvailable_bytes / node_memory_MemTotal_bytes))
rate(container_cpu_usage_seconds_total{image!=""}[5m])
container_memory_usage_bytes{image!=""}
```


## 🌐 Access Points
- 📁 Portfolio App:
  ```http://<your-node-ip>:<your-nodeport>```
- 📈 Grafana:
  ```http://<your-node-ip>:32010```
- 📡 Prometheus:
  ```http://<your-node-ip>:30900```
- 📊 Kubernetes Dashboard:
  ```http://<your-node-ip>:30371```

  
