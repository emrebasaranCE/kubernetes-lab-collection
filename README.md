# Kubernetes Lab 3

In this lab, we dive deeper into Kubernetes configuration by deploying a containerized Node.js application (`app.js`) with persistent storage and dynamic environment configuration.

---

## Steps

1. **Obtain the Lab Files**  
   Start by downloading or cloning the provided lab files, which include the necessary Kubernetes manifests and application code.

2. **Create a Deployment for `app.js`**  
   We define a `Deployment` to manage our Node.js app (`app.js`). This ensures the app is containerized and can scale or recover from failure.

3. **Configure Persistent Storage with Volumes**  
   To persist data beyond the lifecycle of a single pod, we use Kubernetes volumes. This process involves:

   - **Creating a PersistentVolume** (`host-pv.yaml`)  
     This YAML file defines a storage resource on the host machine using `hostPath`.

   - **Creating a PersistentVolumeClaim** (`host-pvc.yaml`)  
     The PVC acts as a request for storage and binds to the defined PersistentVolume.

   - **Mounting the Volume in the Deployment**  
     We reference the PVC in our `deployment.yaml`, mounting it into the container so the app can read from and write to a persistent directory.

4. **Use ConfigMap for Environment Configuration**  
   We use a `ConfigMap` (`environment.yaml`) to inject environment variables into the container — specifically the `STORY_FOLDER` path.  
   This approach follows Kubernetes best practices and allows us to:

   - Keep configuration separate from code
   - Easily update runtime settings without modifying or rebuilding the image
   - Promote reuse and portability across different environments

---

## Summary

This lab covers several foundational Kubernetes concepts:

- **Deployments** – Manage application pods and ensure high availability
- **Persistent Volumes & Volume Claims** – Enable persistent storage across pod lifecycles
- **ConfigMaps** – Provide dynamic, externalized configuration to containers

By the end of this lab, you will have a solid understanding of how to persist data, inject configuration, and manage containerized workloads in a Kubernetes cluster.
