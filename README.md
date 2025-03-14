# 📞 Phonebook-Kubernetes Projec
## 🏗️ Microservice Architecture for Phonebook Web Application (Python Flask) with MySQL using Kubernetes
### 📌 Description
The **Phonebook Microservice Web Application** is designed to provide hands-on experience in deploying a **microservice-based** web application with **MySQL** using **Docker** and **Kubernetes**. This project consists of three main services:

- **Frontend Service**: Handles search operations.
- **Backend Service**: Manages create, update, and delete operations.
- **Database Service**: MySQL database with persistent storage.

Each service is managed through **Kubernetes deployments**, with secrets, config maps, and persistent volumes ensuring data integrity and security. 🚀
---
## 🔥 Problem Statement

Your team is tasked with deploying a **Phonebook Web Application** as a microservice-based web service project.

### 📂 Database Schema

| Field    | Data Type | Description                        |
| -------- | --------- | ---------------------------------- |
| `id`     | Integer   | Unique identifier (auto-increment) |
| `name`   | String    | Name of the contact                |
| `number` | String    | Phone number of the contact        |

### 🌍 RESTful API Endpoints

| HTTP Method | Action                    | Endpoint Example                     |
| ----------- | ------------------------- | ------------------------------------ |
| **GET**     | Read all records          | `http://[ec2-hostname]:30001/`       |
| **POST**    | Create a new record       | `http://[ec2-hostname]:30001/add`    |
| **POST**    | Update an existing record | `http://[ec2-hostname]:30001/update` |
| **POST**    | Delete an existing record | `http://[ec2-hostname]:30001/delete` |
| **POST**    | Search a record           | `http://[ec2-hostname]:30002`        |

---

## ☁️ Deployment on AWS EC2 using Kubernetes

As a **Cloud Engineer**, your goal is to deploy this application on **AWS EC2** instances using **Docker** and **Kubernetes**.

### 🚀 Steps to Deploy

1. **Clone the repository** from GitHub.
2. **Create Docker images** for backend (create/update/delete) and frontend (search).
3. **Deploy services using Kubernetes**:
   - **Database Service** (MySQL) 🛢️
   - **Backend Service** (Create/Update/Delete) ⚙️
   - **Frontend Service** (Search) 🔍
4. **Use Persistent Volumes** to retain data.
5. **Secure sensitive data** using **Kubernetes Secrets**.
6. **Expose services** using Kubernetes **NodePort** and **ClusterIP**.
7. **Ensure high availability** using multiple replicas.

---

## 🏗️ Kubernetes Architecture

### 1️⃣ **Backend (Create/Delete/Update) Service**

- Runs on **port 80**.
- Uses **Kubernetes Secrets** for password management.
- Uses **ConfigMap** to define database host.
- Exposed via **NodePort (30001)**.

### 2️⃣ **Frontend (Search) Service**

- Runs on **port 80**.
- Uses **Kubernetes Secrets** for password management.
- Uses **ConfigMap** to define database host.
- Exposed via **NodePort (30002)**.

### 3️⃣ **Database (MySQL) Service**

- Runs on **port 3306**.
- Uses **Persistent Volume (20Gi)** with **ReadWriteOnce** access mode.
- Exposed via **ClusterIP** (Internal communication only).

---

## 🖥️ Kubernetes Setup

### 🎯 **Infrastructure Requirements**

- **Two EC2 Instances** (1 Master, 1 Worker)
- **Instance Type:** Minimum **t2.medium**
- **Kubernetes Cluster Setup**

### 📌 **Kubernetes Objects**

| Component               | Type                 | Notes                                   |
| ----------------------- | -------------------- | --------------------------------------- |
| **Backend Deployment**  | Deployment           | Handles create/update/delete operations |
| **Backend Service**     | NodePort (30001)     | Exposes backend to the internet         |
| **Frontend Deployment** | Deployment           | Handles search operations               |
| **Frontend Service**    | NodePort (30002)     | Exposes frontend to the internet        |
| **Database Deployment** | Deployment           | Runs MySQL database                     |
| **Database Service**    | ClusterIP            | Internal access only                    |
| **Persistent Volume**   | PV/PVC               | Stores MySQL data                       |
| **Secrets**             | Kubernetes Secret    | Securely store DB credentials           |
| **ConfigMap**           | Kubernetes ConfigMap | Store database connection details       |

---

## 🎯 Goals & Outcomes

✅ **Deploy a scalable microservice-based web application**
✅ **Use Kubernetes for container orchestration**
✅ **Implement persistent storage for MySQL**
✅ **Ensure security with Kubernetes Secrets**
✅ **Expose services using Kubernetes networking**
✅ **Deploy on AWS EC2 instances**

---

## 📜 License

This project is licensed under the **MIT License**.

### 🤝 Contributing

Contributions are welcome! Feel free to open an issue or submit a pull request. 💡

🔗 **GitHub Repo:[ https://github.com/aredo01/phonebook-kubernetes.git] 🚀


## Resources

- [Kubernetes Documentations](https://kubernetes.io/docs/home/)
