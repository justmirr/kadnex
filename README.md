# KADNEX

## What Is This Project?
This project is an advanced demonstration of a cloud-native web application deployment using modern DevOps practices and infrastructure-as-code principles. It involves building a React-based single-page application (SPA) served by NGINX, deployed across three Docker containers, and load-balanced by two HAProxy containers, all orchestrated by a Kubernetes cluster.

Uniquely, the Kubernetes cluster (using k3s) runs entirely within a single AWS EC2 instance, provisioned and configured using Terraform and Ansible. The project leverages Git and GitHub for version control, with a fully automated CI/CD pipeline implemented via GitHub Actions to build, push, and deploy Docker images to the cluster. The result is a scalable, containerized web application hosted on AWS, showcasing end-to-end automation from infrastructure provisioning to application deployment.

---

## Architecture & Technology Stack

### **1. Linux (Ubuntu)**
- **Role:** Operating system for the EC2 instance hosting the Kubernetes cluster.
- **Why:** Provides a stable, open-source environment optimized for container runtimes and Kubernetes, with broad community support.

### **2. Terraform**
- **Role:** Provisions AWS infrastructure (VPC, EC2 instance) as code.
- **Why:** Enables reproducible, version-controlled infrastructure deployment, aligning with IaC best practices.

### **3. AWS (EC2)**
- **Role:** Cloud provider hosting the single EC2 instance.
- **Why:** Offers scalable compute resources and integrates seamlessly with Terraform and Docker registries (ECR), making it ideal for a cloud-native setup.

### **4. Ansible**
- **Role:** Configures the EC2 instance with necessary tools (Docker, kubectl).
- **Why:** Complements Terraform by handling post-provisioning configuration, ensuring the instance is ready for Kubernetes and container workloads.

### **5. Docker**
- **Role:** Containerizes the React/NGINX application and HAProxy.
- **Why:** Provides lightweight, portable application packaging, enabling consistent deployment across environments and Kubernetes pods.

### **6. Kubernetes (k3s)**
- **Role:** Orchestrates the deployment of five Docker containers (three React, two HAProxy) within the EC2 instance.
- **Why:** k3s is a lightweight Kubernetes distribution tailored for resource-constrained environments like a single VM, offering full orchestration capabilities with minimal overhead.

### **7. Git/GitHub**
- **Role:** Version control for application code, Terraform configs, and Kubernetes manifests.
- **Why:** Facilitates collaboration, change tracking, and integration with CI/CD pipelines.

### **8. GitHub Actions**
- **Role:** Automates the CI/CD pipeline to build Docker images, push to ECR, and deploy to k3s.
- **Why:** Provides a free, integrated CI/CD solution within GitHub, streamlining the deployment process.

### **9. NGINX/React Application**
- **Role:** Serves a dynamic web frontend in three containers.
- **Why:** NGINX is a high-performance web server, and React offers a modern, component-based UI framework, simulating a real-world web app.

### **10. HAProxy**
- **Role:** Balances HTTP traffic across the three React containers in two instances.
- **Why:** Ensures high availability and efficient load distribution, demonstrating a critical microservices pattern.

---

## Current Development Status
This project is currently under development, and various components are being integrated and tested. Future updates will include detailed deployment instructions, CI/CD automation steps, and scaling enhancements.
