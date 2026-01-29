# Kubernetes Voting App – Pod vs Deployment

## 📌 Project Overview

This project demonstrates how to deploy a Voting Application on Kubernetes using two different approaches:

1. Using Pod + Service

2. Using Deployment + Service

---

# Directory Structure

```
kubernetes-voting-app
│
├── pod-definition/
│   ├── db-pod.yaml
│   ├── db-service.yaml
│   ├── redis-pod.yaml
│   ├── redis-service.yaml
│   ├── vote-pod.yaml
│   ├── vote-service.yaml
│   ├── result-pod.yaml
│   ├── result-service.yaml
│   └── worker-pod.yaml
│
├── deployment-definition/
│   ├── db-deployment.yaml
│   ├── db-service.yaml
│   ├── redis-deployment.yaml
│   ├── redis-service.yaml
│   ├── vote-deployment.yaml
│   ├── vote-service.yaml
│   ├── result-deployment.yaml
│   ├── result-service.yaml
│   └── worker-deployment.yaml
│
└── README.md
```

---

## The main objective of this project is to clearly understand:

🔹 What is a Pod

🔹 What is a Deployment

🔹 Limitations of using Pods directly

🔹 Why Deployments are preferred in real‑world Kubernetes environments


**This project is beginner‑friendly and ideal for learning Kubernetes fundamentals.**


---

## 📑 Table of Contents

1. Project Overview

2. Directory Structure

3. What is the Voting App?

4. What is a Pod?

5. What is a Deployment?

6. Pod vs Deployment Comparison

7. How to Run This Project

8. Conclusion

9. Skills Demonstrated


## 🗳️ What is the Voting App?

The Voting App is a sample microservices-based application used to learn container orchestration with Kubernetes.

**It consists of:**

* Vote App – Frontend for voting

* Result App – Displays voting results

* Worker – Processes votes

* Redis – Temporary storage

* PostgreSQL – Persistent database*


**This project deploys the same app twice:**

* Once using Pods

* Once using Deployments

**In this project, we focus on deploying the Voting App frontend and exposing it using a Kubernetes Service.**

---

## 🧩 What is a Pod?

A Pod is the smallest and simplest unit in Kubernetes.

🔹 Key Points:

**A Pod runs one or more containers**

Containers inside a Pod share:

🔹 Network

🔹 Storage

**Pods are not self-healing**


## 📄 Pod Usage in This Project

We first deploy the Voting App using a Pod definition file and expose it using a NodePort Service.

## ⚠️ Limitations of Pod

*❌ No auto-recovery if Pod crashes*

*❌ No scaling support*

*❌ No rolling updates*

*❌ Manual recreation required*


➡️ Pods are not recommended for production applications.


---

## 🧱 What is a Deployment?

A Deployment is a higher-level Kubernetes object that manages Pods automatically.

🔹 Key Points:

* **Ensures the desired number of Pods are always running**

* **Provides self-healing**

* **Supports scaling**

* **Enables rolling updates and rollbacks**


## 📄 Deployment Usage in This Project

The Voting App is deployed using a Deployment definition file with multiple replicas and exposed using the same Service.


---

## ⚖️ Pod vs Deployment Comparison

| Feature |	Pod	| Deployment |
|---------|-----|------------|
| Self-healing |❌ No |✅ Yes|
| Scaling	|❌ No|✅ Yes|
| Rolling updates|❌ No|✅ Yes|
| Rollback support |❌ No|✅ Yes|
| Production ready |❌ No|✅ Yes|
| Management | Manual | Automated |

---

## ▶️ How to Run This Project

**1️⃣ Clone the Repository**

```
git clone https://github.com/devops-nikki/Kubernetes-voting-app-pod-vs-deployment.git
cd Kubernetes-voting-app-pod-vs-deployment
```

---

**2️⃣ Deploy Using Pods**

```
kubectl apply -f pod-definition/
```

**Check resources:**

```
kubectl get pods
kubectl get svc
```

---

**3️⃣ Deploy Using Deployments**

```
kubectl apply -f deployment-definition/
```

**Check deployments:**

```
kubectl get deployments
kubectl get pods
kubectl get svc
```

---

**4️⃣ Access the Application**

**If using Minikube:**

```
minikube service vote-service
minikube service result-service
```


---

## ✅ Which One is Better?

* **✔️ Deployment is Better**

### Reasons:

🔹Automatically recreates failed Pods

🔹Easy horizontal scaling using replicas

🔹Zero-downtime updates

🔹Suitable for real-world production workloads


## 🧪 When to Use Pod?

*Learning Kubernetes basics*

*Testing and debugging*

*Temporary workloads*

---

## 📌 Conclusion

*This project clearly shows why Deployments are preferred over Pods in Kubernetes.*

While Pods help understand basic concepts, Deployments provide:

* Reliability

* Scalability

* Automation


👉 Always use Deployments for production workloads.

**In this project:**

*We deployed the Voting App using Pod + Service to understand the basics*

*Then improved the setup using Deployment + Service*


**👉 Deployments are preferred over Pods for any real application due to reliability, scalability, and maintainability.**

---

### 🎯 Interview Tip

**Question: Why should we use Deployment instead of Pod?**

Answer: Pods do not provide self-healing or scaling, whereas Deployments manage Pods automatically and are suitable for production environments.


---

## 🚀 Skills Demonstrated

🔹Kubernetes Pods

🔹Kubernetes Deployments

🔹Kubernetes Services (NodePort)

🔹YAML configuration

🔹Application exposure

🔹DevOps fundamentals

---

**⭐ If you find this project helpful, feel free to star the repository!**