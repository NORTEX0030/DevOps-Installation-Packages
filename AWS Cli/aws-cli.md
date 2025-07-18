# ☁️ Installing AWS CLI v2 on Linux

The AWS Command Line Interface (CLI) lets you interact with AWS services from the terminal. This guide walks through installing **AWS CLI v2** on major Linux distributions.

---

## 🐧 Ubuntu / Debian

### ✅ Step 1: Download the Installer

```bash
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install

```

Imp: install unzip
```bash
sudo install unzip
```

✅ Step 2: Unzip the Installer
```bash
unzip awscliv2.zip
```
✅ Step 3: Install AWS CLI
```bash
sudo ./aws/install

    📌 If upgrading, use:

    sudo ./aws/install --update
```
📦 RHEL / CentOS
✅ Step 1: Install Unzip (if not installed)
```bash
sudo yum install unzip -y
```
✅ Step 2: Download & Unzip AWS CLI Installer
```bash
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o 
"awscliv2.zip"

unzip awscliv2.zip
```
✅ Step 3: Install AWS CLI
```bash
sudo ./aws/install
```
🔍 Verify Installation
```bash
aws --version
```
Expected output:

aws-cli/2.x.x Python/3.x.x Linux/x86_64

⚙️ Configure AWS CLI
```bash
aws configure
```
You'll be prompted to enter:

- AWS Access Key ID

- AWS Secret Access Key

- Default region (e.g., us-east-1)

- Output format (e.g., json)

🧪 Test CLI Access
```bash
aws sts get-caller-identity
```
This command verifies your credentials and returns your IAM identity.


🔧 Useful AWS CLI Commands
| Task                  | Command                                       |
| --------------------- | --------------------------------------------- |
| List S3 buckets       | `aws s3 ls`                                   |
| Start EC2 instance    | `aws ec2 start-instances --instance-ids <id>` |
| View IAM users        | `aws iam list-users`                          |
| Describe EKS clusters | `aws eks list-clusters`                       |
| Upload file to S3     | `aws s3 cp file.txt s3://your-bucket-name/`   |


🧹 Clean Up
```bash
rm -rf awscliv2.zip aws/
```

✅ AWS CLI is now installed and ready to use for managing your cloud infrastructure!
