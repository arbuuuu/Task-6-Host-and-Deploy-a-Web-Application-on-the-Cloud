# Task-6-Host and Deploy a Web Application on AWS (S3 Static Hosting)
Deploy a **static or dynamic web application** (like a simple portfolio or basic HTML app) on a cloud platform using a **virtual machine, App Engine, or web hosting service**.

# ☁️ Task 6: Host and Deploy a Web Application on AWS (S3)

## 🎯 Objective
To deploy a **static web application** (like a portfolio or simple HTML app) on **Amazon S3** — a scalable cloud storage service that also supports website hosting.

---

## 🛠️ Tools
- **Cloud Platform:** Amazon Web Services (AWS)
- **Service Used:** Amazon S3 (Simple Storage Service)
- **Local Tools:** VS Code, Git, Web Browser

---


---

## 🚀 Step-by-Step Deployment on AWS S3

### **1️⃣ Create S3 Bucket**
1. Sign in to your **AWS Console** → Go to **S3**.
2. Click **Create bucket**.
3. Give it a unique name (e.g., `my-aws-cloud-app`).
4. **Uncheck** “Block all public access”.
5. Click **Create bucket**.

---

### **2️⃣ Upload Website Files**
1. Open your bucket → Go to **Objects** → Click **Upload**.
2. Upload:
   - `index.html`
   - Entire `assets` folder.
3. Click **Upload**.

---

### **3️⃣ Enable Static Website Hosting**
1. Go to your bucket → **Properties tab**.
2. Scroll to **Static website hosting** → Click **Edit**.
3. Enable it and enter:
   - **Index document:** `index.html`
4. Save changes.

---

### **4️⃣ Make Your Website Public**
1. Go to the **Permissions** tab.
2. Under **Block public access (bucket settings)** → Click **Edit** → Uncheck all boxes.
3. Acknowledge the warning and **Save changes**.

---

### **5️⃣ Add Bucket Policy**
Go to **Bucket Policy** → Click **Edit** → Paste the policy below  
(Replace `my-aws-cloud-app` with your bucket name):

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::my-aws-cloud-app/*"
    }
  ]
}

6️⃣ Access Your Hosted Website

Go to Properties → Static website hosting.

Copy the Website endpoint URL (e.g.):

http://my-aws-cloud-app.s3-website-us-east-1.amazonaws.com


Open it in your browser → you’ll see:

Hello Cloud!
This is my first web app hosted on AWS S3.
