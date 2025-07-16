# ⚙️ Installing Ansible on Linux

[Ansible](https://www.ansible.com/) is an open-source configuration management, provisioning, and deployment tool. This guide covers Ansible installation on popular Linux distributions.

---

## 🐧 Ubuntu / Debian

### ✅ Step 1: Update and Install Required Packages

```bash
sudo apt update
sudo apt install -y software-properties-common


```
✅ Step 2: Add Ansible PPA

```bash
sudo add-apt-repository --yes --update ppa:ansible/ansible

```
✅ Step 3: Install Ansible

```bash
sudo apt install -y ansible

```
📦 RHEL / CentOS
✅ Step 1: Enable EPEL Repository

```bash
sudo yum install epel-release -y

```
✅ Step 2: Install Ansible

```bash
sudo yum install ansible -y

```
🔍 Verify Installation

```bash
ansible --version

```
Expected output:

```bash
ansible [core 2.x.x]
config file = /etc/ansible/ansible.cfg


```
🧪 Test Ansible with Ping Module

Create an inventory file:

```bash
# inventory.ini
[local]
localhost ansible_connection=local

```
Run a ping test:

```bash
ansible -i inventory.ini local -m ping

```
Output should be:

```bash
localhost | SUCCESS => {
    "changed": false,
    "ping": "pong"
}

```
📁 Default File Locations

| Path                        | Description             |
| --------------------------- | ----------------------- |
| `/etc/ansible/ansible.cfg`  | Default config file     |
| `/etc/ansible/hosts`        | Default inventory file  |
| `/usr/bin/ansible`          | Main Ansible executable |
| `/usr/bin/ansible-playbook` | Playbook runner         |



📘 Tips

- Use YAML (.yml) files to write playbooks.

- Group your hosts in inventory files for better management.

- Secure credentials using ansible-vault.