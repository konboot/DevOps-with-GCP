## 🧱 What is Compute Engine?

- Compute Engine is GCP’s **IaaS** (Infrastructure as a Service) that lets you launch **virtual machines** (VMs) on demand.
- VMs are customizable by CPU, RAM, OS, boot disk, and networking.
- Supports **automated provisioning**, **startup scripts**, **auto-healing**, and **custom images**.

---

---

## 🧪 Hands-On Lab

### 🛠️ Launch a VM and Connect via SSH

    gcloud compute instances create devops-vm \
      --zone=us-central1-a \
      --machine-type=e2-micro \
      --image-family=ubuntu-2004-lts \
      --image-project=ubuntu-os-cloud \
      --tags=http-server

    # SSH into the instance
    gcloud compute ssh devops-vm --zone=us-central1-a

---

### 🛠️ Manually Install NGINX on Ubuntu VM

Once inside the VM via SSH, run the following:

    sudo apt update
    sudo apt install -y nginx
    sudo systemctl enable nginx
    sudo systemctl start nginx

To test:

    curl http://localhost

---

### 🛠️ Install NGINX Automatically via Startup Script

    gcloud compute instances create nginx-vm \
      --zone=us-central1-a \
      --machine-type=e2-micro \
      --image-family=ubuntu-2004-lts \
      --image-project=ubuntu-os-cloud \
      --metadata startup-script='#! /bin/bash
    apt update
    apt install -y nginx
    systemctl enable nginx
    systemctl start nginx' \
      --tags=http-server

---

### 🛠️ Enable Firewall Rule for HTTP Access

    gcloud compute firewall-rules create allow-http \
      --allow tcp:80 \
      --target-tags=http-server \
      --description="Allow HTTP traffic" \
      --direction=INGRESS \
      --priority=1000 \
      --network=default

---

### 🛠️ Create a Custom Image from Existing VM

    # Stop the VM before creating image
    gcloud compute instances stop nginx-vm --zone=us-central1-a

    # Create image from disk
    gcloud compute images create nginx-custom-image \
      --source-disk=nginx-vm \
      --source-disk-zone=us-central1-a

    # Launch a new VM from custom image
    gcloud compute instances create nginx-from-image \
      --zone=us-central1-a \
      --machine-type=e2-micro \
      --image=nginx-custom-image \
      --tags=http-server

---
