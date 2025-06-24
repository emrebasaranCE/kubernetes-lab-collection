# Kubernetes Lab Collection

Welcome to **Kubernetes Lab Collection** – a monorepo gathering all of my Kubernetes hands-on labs in one place for easier navigation, shared tooling, and unified CI.

---

## Repository Structure

Each lab lives in its own folder, preserving its full Git history:

* **k8s-101/**

  * Introductory covering Kubernetes architecture.

* **kubernetes\_lab\_001/**

  * Lab 001: Core concepts and object definitions (Pods, Deployments, Services). See `kubernetes_lab_001/README.md` for details.

* **kubernetes\_lab\_002/**

  * Lab 002: Walks through deploying a containerized Node.js application backed by PersistentVolumes and PersistentVolumeClaims for durable storage, with dynamic environment variables injected via a ConfigMap. See `kubernetes_lab_002/README.md`.

* **kubernetes\_lab\_003/**

  * Lab 003: Deploy and expose three distinct microservices (auth_api, tasks_api, users_api) as individual pods with their own Services and to establish DNS-based inter-service communication in a stateless, ephemeral Kubernetes environment. See `kubernetes_lab_003/README.md`.

---

## Getting Started

1. **Clone the monorepo**

   ```bash
   git clone git@github.com:emrebasaranCE/kubernetes-lab-collection.git
   cd kubernetes-lab-collection
   ```

2. **Choose a lab**

   ```bash
   cd k8s-101         # or kubernetes_lab_001, kubernetes_lab_002, kubernetes_lab_003
   ```

3. **Follow the lab-specific instructions**
   Each lab folder contains its own README and scripts. For example:

   ```bash
   cat kubernetes_lab_001/README.md
   ```

---

## Adding a New Lab

To import another existing lab repository while preserving its history, use:

```bash
git remote add labNNN <repo-url>
 git fetch labNNN
 git subtree add --prefix=labNNN/ labNNN <branch>
 git remote remove labNNN
 git push origin main
```

Replace `labNNN`, `<repo-url>`, and `<branch>` (usually `main` or `master`).

---

## Common Utilities (Optional)

If you have shared scripts or configurations, consider moving them into a `common/` directory and referencing them from each lab.

---

*Happy clustering!*
