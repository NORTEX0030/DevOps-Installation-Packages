# 🛠️ Installing Terraform on Linux

Terraform by HashiCorp is an open-source infrastructure as code tool used to provision and manage infrastructure efficiently. This guide shows how to install Terraform on various Linux distributions.

---

## 🐧 Ubuntu / Debian

### ✅ Step 1: Install Required Dependencies

```bash
sudo apt update && sudo apt install -y gnupg software-properties-common curl
```
✅ Step 2: Add HashiCorp GPG Key

```bash
curl -fsSL https://apt.releases.hashicorp.com/gpg | sudo gpg 
--dearmor -o /usr/share/keyrings/hashicorp-archive-keyring.gpg
```
✅ Step 3: Add HashiCorp Repo

```bash
echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] \
https://apt.releases.hashicorp.com $(lsb_release -cs) main" | \
sudo tee /etc/apt/sources.list.d/hashicorp.list
```
✅ Step 4: Install Terraform

```bash
sudo apt update && sudo apt install terraform -y
```
📦 RHEL / CentOS
✅ Step 1: Add HashiCorp Repo

```bash
sudo yum install -y yum-utils
sudo yum-config-manager --add-repo https://rpm.releases.hashicorp.
com/RHEL/hashicorp.repo
```
✅ Step 2: Install Terraform

```bash
sudo yum install terraform -y
```
🔍 Verify Installation

```bash
terraform version

```
Output should show the installed Terraform version.

🔄 Upgrade Terraform (Any OS)

If you want to upgrade to the latest version:

```bash
sudo apt update && sudo apt upgrade terraform -y   # Debian/Ubuntu
sudo yum update terraform -y                       # RHEL/CentOS
```
⚙️ First-Time Initialization

Once installed, initialize any Terraform project with:

```bash
terraform init
```
📁 Default Terraform Directory Structure

| File/Folder         | Purpose                                |
| ------------------- | -------------------------------------- |
| `main.tf`           | Main configuration file                |
| `variables.tf`      | Input variables declaration            |
| `outputs.tf`        | Output values definition               |
| `terraform.tfvars`  | Actual variable values                 |
| `.terraform/`       | Terraform working directory (auto-gen) |
| `terraform.tfstate` | State file (tracks infrastructure)     |





✅ Terraform is now installed and ready to use!
You can start defining infrastructure as code using .tf files.