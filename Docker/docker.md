# 🐳 Installing Docker on Linux

Docker is a platform for developing, shipping, and running applications in containers. This guide provides step-by-step instructions to install Docker on common Linux distributions.

---

## 🐧 Ubuntu / Debian

### ✅ Step 1: Update and Install Prerequisites

```bash
sudo apt update
sudo apt install \
    ca-certificates \
    curl \
    gnupg \
    lsb-release -y
```

✅ Step 2: Add Docker’s Official GPG Key

```bash
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | \
    sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg

```

✅ Step 3: Set Up the Docker Repository

```bash
echo \
  "deb [arch=$(dpkg --print-architecture) \
  signed-by=/etc/apt/keyrings/docker.gpg] \
  https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

```

✅ Step 4: Install Docker Engine

```
sudo apt update
sudo apt install docker-ce docker-ce-cli containerd.io 
docker-buildx-plugin docker-compose-plugin -y

```

✅ Step 5: Verify Docker Installation

```

docker --version

```

---
# 📦 RHEL / CentOS


✅ Step 1: Install Required Packages
```bash
sudo yum install -y yum-utils

```
✅ Step 2: Add Docker Repository
```
sudo yum-config-manager \
    --add-repo \
    https://download.docker.com/linux/centos/docker-ce.repo
```
✅ Step 3: Install Docker Engine
```bash
sudo yum install docker-ce docker-ce-cli containerd.io 
docker-buildx-plugin docker-compose-plugin -y
```
✅ Step 4: Start and Enable Docker
```bash
sudo systemctl start docker
sudo systemctl enable docker
```
✅ Step 5: Verify Docker Installation
```bash
docker --version
```
👤 Optional: Run Docker as Non-Root User
```bash
sudo usermod -aG docker $USER
newgrp docker
```
 📌 Log out and back in for the changes to take effect.

🔧 Test Docker with Hello World
```bash
docker run hello-world
```

✅ Docker Installed Successfully!
You can now start using containers on your Linux system.