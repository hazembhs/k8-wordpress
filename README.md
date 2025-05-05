
# 🚀 Kubernetes WordPress Deployment

This project demonstrates the deployment of a scalable, production-ready **WordPress application on Kubernetes**, built with best practices for container orchestration, monitoring, persistence, and automation. Designed to reflect real-world DevOps scenarios, it showcases my hands-on ability to manage cloud-native applications, infrastructure-as-code, and cluster observability.

> 💡 **Why this project?**  
> As a DevOps engineer passionate about scalable systems, I built this to showcase infrastructure automation, resilient app deployment, and monitoring integration — all critical in cloud environments.

---

## 📦 What's Inside

A full-stack Kubernetes setup including:

- 📝 **WordPress**: Containerized CMS application
- 🛢️ **MySQL**: Backed with persistent volume via StatefulSet
- ⚡ **Redis**: For caching, deployed as a StatefulSet
- 📈 **Monitoring**: Includes Prometheus exporters for MySQL & Redis
- 🔁 **Horizontal Pod Autoscaler**: Dynamic scaling for WordPress
- 🔐 **Secrets & ConfigMaps**: Secure credential and config handling
- 🧪 **Modular YAML Manifests**: All components defined as IaC (Infrastructure as Code)

---

## 🗂️ Repository Structure

```bash
.
├── wordpress-deployment.yaml
├── wordpress-service.yaml
├── wordpress-pvc.yaml
├── wordpress-hpa.yaml
├── mysql-statefulset.yaml
├── mysql-service.yaml
├── mysql-pvc.yaml
├── mysql-secret.yaml
├── redis-statefulset.yaml
├── redis-service.yaml
├── mysql-exporter.yaml
├── redis-exporter.yaml
├── service-monitor.yaml
├── components.yaml
├── .my.cnf
└── .gitignore
```

---

## 🛠️ How to Deploy

### 1. Clone the repository:
```bash
git clone https://github.com/hazembhs/k8-wordpress.git
cd k8-wordpress
```

### 2. Deploy MySQL
```bash
kubectl apply -f mysql-secret.yaml
kubectl apply -f mysql-pvc.yaml
kubectl apply -f mysql-statefulset.yaml
kubectl apply -f mysql-service.yaml
```

### 3. Deploy Redis
```bash
kubectl apply -f redis-statefulset.yaml
kubectl apply -f redis-service.yaml
```

### 4. Deploy WordPress
```bash
kubectl apply -f wordpress-pvc.yaml
kubectl apply -f wordpress-deployment.yaml
kubectl apply -f wordpress-service.yaml
kubectl apply -f wordpress-hpa.yaml
```

### 5. Deploy Monitoring
```bash
kubectl apply -f mysql-exporter.yaml
kubectl apply -f redis-exporter.yaml
kubectl apply -f service-monitor.yaml
```

---

## 🌐 Access the App

After deploying:
```bash
kubectl get svc wordpress-service
```
Use the **EXTERNAL-IP** shown to access WordPress in your browser.

---

## 📊 Monitoring & Observability

- **Prometheus Exporters** integrated for:
  - MySQL metrics
  - Redis metrics
- Easily integrable with **Prometheus + Grafana stack** for dashboards.

---

## 👨‍💻 About the Author

Hi, I'm **Hazem**, a DevOps enthusiast with a passion for cloud-native architecture, automation, and building reliable infrastructure. This project is a reflection of my skills in Kubernetes, YAML, CI/CD practices, and scalable deployments. I'm actively seeking opportunities in DevOps/SRE roles where I can contribute to infrastructure excellence and innovation.

---

## 📜 License

Licensed under the [MIT License](LICENSE).

---

> ⭐️ If you find this project helpful or interesting, feel free to star the repo and connect with me on [LinkedIn](https://www.linkedin.com/in/hazem-ben-hadj-salah/).
