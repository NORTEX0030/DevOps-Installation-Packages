# ☸️ Installing Kubernetes (Minikube, kubeadm, kind, EKS)

This document outlines various ways to install and work with Kubernetes for local development and production environments.

---

## 🔹 1. Minikube (Local Kubernetes for Developers)

### ✅ Requirements:

- VirtualBox, Docker, or any supported VM driver
- kubectl installed

### ✅ Installation (Linux):

```bash
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube
```

✅ Start Minikube:
```bash
minikube start --driver=docker
```
✅ Check Status:
```bash
kubectl get nodes
```
🔸 2. kubeadm (Production-like Local or Remote Cluster)
✅ Requirements:

2 or more Linux machines (VMs or bare metal)
Ubuntu 20.04+ or CentOS
Swap disabled

✅ Installation Steps:
```bash
# On all nodes
sudo apt update && sudo apt install -y apt-transport-https curl

curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | 
sudo apt-key add -

echo "deb https://apt.kubernetes.io/ kubernetes-xenial main" | \
  sudo tee /etc/apt/sources.list.d/kubernetes.list

sudo apt update
sudo apt install -y kubelet kubeadm kubectl
sudo apt-mark hold kubelet kubeadm kubectl
```
✅ Initialize Master Node:
```bash
sudo kubeadm init --pod-network-cidr=192.168.0.0/16
```
✅ Set Up kubectl for Current User:
```
mkdir -p $HOME/.kube
sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
sudo chown $(id -u):$(id -g) $HOME/.kube/config
```
✅ Apply Pod Network :
```bash
kubectl apply <pod name>.yaml
```
✅ Join Worker Nodes:
```bash
Copy the kubeadm join command from the output of the init command 
and run it on worker nodes.
```

🔹 3. kind (Kubernetes IN Docker)

Perfect for CI/CD or quick local testing.
✅ Install kind:
```bash
curl -Lo ./kind https://kind.sigs.k8s.io/dl/latest/kind-linux-amd64
chmod +x kind
sudo mv kind /usr/local/bin
```
✅ Create a Cluster:
```bash
kind create cluster
```
✅ Check Nodes:
```bash
kubectl get nodes
```
✅ Delete Cluster:
```bash
kind delete cluster
```
🔸 4. Amazon EKS (Elastic Kubernetes Service)
✅ Prerequisites:

    AWS CLI configured (aws configure)

    kubectl installed

    eksctl installed

✅ Install eksctl:
```bash
curl --silent --location "https://github.com/eksctl-io/eksctl/releases/latest/download/eksctl_$(uname -s)_amd64.tar.gz" | tar xz -C /tmp
sudo mv /tmp/eksctl /usr/local/bin
```
✅ Create EKS Cluster:
```bash
eksctl create cluster --name my-eks-cluster --region us-east-1 --nodes 2
```
⏳ This process may take a few minutes.

✅ Check Cluster:
```bash
kubectl get svc
kubectl get nodes
```
✅ Delete EKS Cluster:
```bash
eksctl delete cluster --name my-eks-cluster --region us-east-1
```
🧪 Test Your Kubernetes Setup
```bash
kubectl create deployment nginx --image=nginx
kubectl expose deployment nginx --port=80 --type=NodePort
kubectl get pods
kubectl get svc
```
✅ Kubernetes is now installed using your preferred method!
Use kubectl to manage your clusters and deploy applications.