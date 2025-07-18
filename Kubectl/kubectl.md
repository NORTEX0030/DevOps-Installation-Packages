# ☸️ Installing kubectl (Kubernetes CLI)

`kubectl` is the command-line tool for interacting with Kubernetes clusters. This guide provides step-by-step instructions for installing and verifying `kubectl` on Linux systems.

---

## 🐧 Ubuntu / Debian

### ✅ Step 1: Download the Latest kubectl Binary

```bash
curl -LO "https://dl.k8s.io/release/$(curl -sL https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
chmod +x kubectl
sudo mv kubectl /usr/local/bin/


```
✅ Step 2: Make the Binary Executable
```bash
chmod +x kubectl
```
✅ Step 3: Then confirm:
```bash
kubectl version --client

```
---
📦 RHEL / CentOS

Same process as Ubuntu:
```bash
curl -LO "https://dl.k8s.io/release/$(curl -sL https://dl.k8s.io/
release/stable.txt)/bin/linux/amd64/kubectl"
chmod +x kubectl
sudo mv kubectl /usr/local/bin/
```
🔍 Verify Installation
```bash
kubectl version --client
```
Expected output:
```bash
Client Version: vX.Y.Z
```
✅ You're now ready to manage Kubernetes clusters using kubectl.

⚙️ Set Up kubectl to Use a Cluster

For example, if using minikube:
```bash
minikube start
kubectl get nodes
```
For kubeadm:
```bash
# After kubeadm init on master node
mkdir -p $HOME/.kube
sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
sudo chown $(id -u):$(id -g) $HOME/.kube/config
```
For AWS EKS (via eksctl):
```bash
eksctl create cluster --name demo --region us-east-1
kubectl get svc
```
