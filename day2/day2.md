# 📘 Day 2 — Install Minikube: Setup Your First Kubernetes Cluster

Welcome to **Day 2** of the *"Learn Kubernetes Day by Day"* series!

Today, you'll set up a **local Kubernetes environment** using **Minikube**.  
This is a crucial step that will let you interact with real Kubernetes resources in the coming days.

---

## 🧰 What is Minikube?

**Minikube** is a lightweight tool that runs a single-node Kubernetes cluster on your local machine.  
It's perfect for:

- 🧪 Development and testing  
- 👨‍🎓 Learning Kubernetes without the cloud  
- 💻 Working fully offline after setup  

> ✅ Supports Docker, VirtualBox, KVM, Hyper-V, Podman, and more.

---

## ✅ Minimum Requirements

Make sure your machine meets these requirements:

| Resource       | Minimum Requirement       |
|----------------|--------------------------|
| CPU            | 2 cores                  |
| RAM            | 2 GB                     |
| Disk Space     | 20 GB                    |
| Internet       | Required for installation|
| Container/VM   | Docker, VirtualBox, etc. |

---

## 🔧 Step-by-Step Installation (Linux)

> 🖥️ **For Windows/macOS**, see the [official guide](https://minikube.sigs.k8s.io/docs/start/).

### 1. Download and Install Minikube

```bash
curl -LO https://github.com/kubernetes/minikube/releases/latest/download/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube
rm minikube-linux-amd64
```

Verify the installation:

```bash
minikube version
```

---

### 2. Start Your First Kubernetes Cluster

Start your local Kubernetes cluster:

```bash
minikube start
```

This command will:

- 🔍 Detect your installed driver (Docker, VirtualBox, etc.)
- 📦 Download the necessary Kubernetes binaries
- ⚙️ Launch a local single-node Kubernetes cluster

> 🕐 **Note:** The first startup may take a few minutes depending on your hardware and internet speed.

---

### 3. Verify That Everything Works

If you already have `kubectl` installed:

```bash
kubectl get nodes
kubectl get pods -A
```

Or use the built-in version provided by Minikube:

```bash
minikube kubectl -- get nodes
minikube kubectl -- get pods -A
```

Optional: Add an alias to simplify your commands:

```bash
alias kubectl="minikube kubectl --"
```

---

## 🧭 What We Won’t Do (Yet)

To stay focused, we **will not**:

- Deploy applications or services
- Use the Kubernetes dashboard
- Expose any ports or services

These topics will be covered in the upcoming days:

- 🔹 Pods & Deployments
- 🔹 Services & LoadBalancers
- 🔹 Volumes & ConfigMaps
- 🔹 Monitoring & Ingress

---

## 🧰 Troubleshooting Tips

If `minikube start` fails:

- ✅ Make sure Docker is running:

    ```bash
    docker ps
    ```

- 🔄 Reset and restart everything:

    ```bash
    minikube delete && minikube start
    ```

- 📄 Check drivers and installation help:  
    👉 [https://minikube.sigs.k8s.io/docs/drivers/](https://minikube.sigs.k8s.io/docs/drivers/)

---

## 📅 What's Next?

**Day 3** — Deploy your first **Pod**, learn what it is, and use `kubectl` to interact with it.

---

📂 *This file is part of the repository: [`learn-kubernetes-day-by-day`](../README.md)*
