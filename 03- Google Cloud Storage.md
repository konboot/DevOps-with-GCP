# Google Cloud Storage services
1. **Cloud Storage (GCS)** – Object storage for unstructured data like logs, artifacts, and backups.  
2. **Filestore** – Managed **NFS file system** for workloads that need shared POSIX file access.  
3. **Local SSDs** – High-performance ephemeral block storage directly attached to VM hosts.  
4. **Bigtable** – Wide-column NoSQL database for large-scale, time-series, or operational data.  
5. **Pub/Sub** – Messaging and event streaming service to connect microservices and trigger workflows.  

---

# 🚀 Demo: Google Cloud Storage with Compute Engine VM

This demo shows how to securely connect **Google Cloud Storage (GCS)** with a **Compute Engine VM** using only the **Google Cloud Console (UI)**.  
By completing it, you’ll practice secure, keyless access to cloud storage.

---

## 🔑 What You Will Learn
- Create and configure a **GCS bucket**.  
- Use **service accounts** for secure IAM-based access.  
- Launch a **Compute Engine VM** with an attached service account.  
- Access GCS from inside the VM (read/write files).  
- Safely **clean up resources** after the demo.  

---

## 📝 Step-by-Step Summary

1. **Create a GCS Bucket**
   - Go to **Cloud Storage → Buckets**.  
   - Create a bucket with a unique name and regional location.  
   - Upload a sample file (e.g., `hello.txt`).  

2. **Create a Service Account**
   - Go to **IAM & Admin → Service Accounts**.  
   - Create a new service account (`gcs-demo-sa`).  
   - Assign the **Storage Object Admin** role.  

3. **Launch a Compute Engine VM**
   - Go to **Compute Engine → VM Instances**.  
   - Create a VM (`gcs-demo-vm`) in the same region.  
   - Attach the service account for GCS access.  

4. **Access GCS from the VM**
   - SSH into the VM from the console.  
   - Use `gcloud storage ls` to list bucket files.  
   - Download and upload files between VM and bucket.  

5. **Cleanup**
   - Delete the **VM**.  
   - Delete the **Bucket**.  
   - Delete the **Service Account**.  
   - (Or delete the entire project if it was created just for this demo).

---
