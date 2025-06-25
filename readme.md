# 💼 Portfolio DevOps Project — Minikube Kubernetes Deployment

This project demonstrates a full DevOps lifecycle by deploying a personal portfolio website on a **local Minikube-based Kubernetes cluster**. It integrates all essential DevOps tools: GitHub, Jenkins, Docker, Kubernetes, and monitoring via Prometheus + Grafana.

---

## 🛠️ Tech Stack

| Category         | Tools/Technologies         |
|------------------|----------------------------|
| Frontend         | HTML, CSS, JavaScript      |
| Version Control  | Git + GitHub               |
| CI/CD            | Jenkins (Pipeline as Code) |
| Containerization | Docker                     |
| Orchestration    | Kubernetes (Minikube)      |
| Monitoring       | Prometheus + Grafana       |

---

## 📁 Folder Structure

```
portfolio-devops-k8s-minikube/
├── index.html                # Static website content
├── Dockerfile                # Builds portfolio image
├── jenkins/
│   └── pipeline              # Jenkins CI/CD pipeline script
├── k8s/
│   ├── deployment.yaml       # Kubernetes deployment
│   └── service.yaml          # Kubernetes NodePort service
├── monitoring/
│   ├── prometheus.yaml       # Prometheus scrape config
│   └── grafana-dashboards/   # Grafana JSON dashboards
```

---

## 🔁 CI/CD Pipeline (Jenkins)

1. **Clone from GitHub**  
2. **Build Docker image** using the `Dockerfile`
3. **Push to DockerHub**
4. **Deploy to Kubernetes** using `kubectl` and `.yaml` files

---

## 📦 Docker Image

- DockerHub: `rahul0941/portfolio-page`
- Built using:
  ```dockerfile
  FROM nginx:alpine
  COPY index.html /usr/share/nginx/html/
  ```

---

## ☸️ Kubernetes Setup (Minikube)

1. **Start Minikube**  
   ```bash
   minikube start
   ```

2. **Deploy app**
   ```bash
   kubectl apply -f k8s/deployment.yaml
   kubectl apply -f k8s/service.yaml
   ```

3. **Access the app**
   ```bash
   minikube service portfolio-service
   ```

---

## 📊 Monitoring with Prometheus + Grafana

- Installed via Helm:
  ```bash
  helm install kube-prometheus-stack prometheus-community/kube-prometheus-stack
  ```

- Prometheus scrape config added via annotations:
  ```yaml
  annotations:
    prometheus.io/scrape: "true"
    prometheus.io/path: "/metrics"
    prometheus.io/port: "8080"
  ```

- Grafana Dashboards:
  - Pods Status
  - CPU/Memory Usage
  - Deployment Health

---

## ✅ Final Output

Deployed site runs locally using Kubernetes with full CI/CD and monitoring enabled.

---

## 🧠 Learning Outcome

- Hands-on with all key DevOps tools
- Real-world CI/CD pipeline experience
- Kubernetes Deployment and Monitoring basics
- Local development and automation using Minikube

---

## 👨‍💻 Author

**Rahul Kumar**  
DevOps Engineer Intern  

