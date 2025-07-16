# 🛠️ Installing NGINX Web Server

NGINX is a high-performance HTTP server, reverse proxy, and IMAP/POP3 proxy server. This guide shows you how to install NGINX on common Linux distributions.

---

## 🐧 Installation on Ubuntu / Debian

Update the package list and install NGINX using `apt`:

```bash
sudo apt update
sudo apt install nginx -y
```

✅ To Start and Enable NGINX:
```bash
sudo systemctl start nginx
sudo systemctl enable nginx
```
🔍 To Check Status:
```bash
sudo systemctl status nginx
```

---

# 📦 Installation on RHEL / CentOS
First, install the EPEL (Extra Packages for Enterprise Linux) repository:

```bash
sudo yum install epel-release -y
```

Then install NGINX:
```bash
sudo yum install nginx -y

```

✅ To Start and Enable NGINX:
```bash
sudo systemctl start nginx
sudo systemctl enable nginx
```

🔍 To Check Status:
```bash
sudo systemctl status nginx
```
---
## 📁 NGINX File Structure (Linux)

| File/Directory                   | Purpose                                      |
|----------------------------------|----------------------------------------------|
| `/etc/nginx/nginx.conf`          | Main configuration file                      |
| `/etc/nginx/sites-available/`    | Stores virtual host (server block) configs   |
| `/etc/nginx/sites-enabled/`      | Symlinks to active site configs              |
| `/var/www/html`                  | Default web root directory                   |
| `/var/log/nginx/`                | Contains access and error logs               |

---

## 🧪 Demo: Run NGINX Using Docker

You can quickly spin up an NGINX container for testing and learning using Docker.

### ✅ Step 1: Run the NGINX Container

```bash
docker run --name nginx-demo -p 8080:80 -d nginx

```
# 🌐 Verify Installation
Open a browser and navigate to:
```bash
http://<your-server-ip>
```
# 📁 Configuration Files
```bash
    Default Config Path: /etc/nginx/nginx.conf

    Site Config Directory (Ubuntu/Debian): /etc/nginx/sites-available/
```

# 🚀 Useful Commands
```bash

| Task               | Command                        |
| ------------------ | ------------------------------ |
| Reload config      | `sudo nginx -s reload`         |
| Test configuration | `sudo nginx -t`                |
| Stop NGINX         | `sudo systemctl stop nginx`    |
| Restart NGINX      | `sudo systemctl restart nginx` |
```