# Kubernetes Lab 3

In this lab, we work with **three different backend services**, each deployed as a container, to understand how microservices communicate within a Kubernetes cluster. Unlike the previous lab, this one **does not focus on data persistence** — meaning all data is ephemeral and will be lost after running `docker-compose down` or deleting the deployment.

---

## Services Overview

- **`auth_api`** – Handles user authentication
- **`tasks_api`** – Stores and returns task data
- **`users_api`** – Manages user creation and login

---

## Deployment Workflow

1. **Initial Setup**  
   We first created `users-deployment.yaml` to deploy the `users_api`.

2. **Exposing the Pod**  
   Then we created `users-service.yaml`, which defines a **LoadBalancer service** to expose the `users_api` pod to external traffic.

3. **Combining Containers (Initial Attempt)**  
   Initially, the `auth_api` was added to the same pod as `users_api` within the `users-deployment.yaml` file.

4. **Refactoring for Best Practice**  
   Upon the instructor's suggestion, we separated the containers into their own deployments, aligning with Kubernetes best practices of **one container per pod**.

5. **Deployment and Service Files Created for Each App:**
   - `auth-deployment.yaml`
   - `auth-service.yaml`
   - `users-deployment.yaml`
   - `users-service.yaml`
   - `tasks-deployment.yaml`
   - `tasks-service.yaml`

6. **Establishing Internal Communication**  
   With each service in its own pod and deployment, communication is achieved via Kubernetes **Service names** (which act as DNS names inside the cluster).

---

## Summary

This lab demonstrates how to:

- Deploy multiple microservices into **separate pods** using individual `Deployment` files.
- Expose each service to the cluster (and optionally the outside world) using `Service` resources.
- Understand the difference between initial co-located containers and **refactored, decoupled services**.
- Establish **inter-pod communication** using Kubernetes service discovery via DNS.
- Operate in a **stateless environment**, where data is not persisted beyond container lifecycle.

This is a foundational step toward mastering service-oriented architecture and inter-service communication within a Kubernetes environment.
