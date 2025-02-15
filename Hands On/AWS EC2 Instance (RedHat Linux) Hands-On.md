# 🚀 AWS EC2 Setup Guide

## 1️⃣ Overview
This guide covers the step-by-step process of setting up an **AWS EC2 Instance (RedHat Linux)**, challenges faced during the setup, how I resolved them, and the final output.

---

## 2️⃣ Steps to Launch an EC2 Instance

### ✅ **Step 1: Log in to AWS Console**
1. Go to [AWS Management Console](https://aws.amazon.com/console/)

![image](https://github.com/user-attachments/assets/3e4c82ef-db75-4bc5-81d4-1ab3bec69921)

2. Search for **EC2** in the AWS services.

![image](https://github.com/user-attachments/assets/288a01a9-abe4-41b4-a766-a2481b8f1fc5)

### ✅ **Step 2: Launch an Instance**
1. Click **Launch Instance**.

![image](https://github.com/user-attachments/assets/e568beea-f2a0-4e73-9655-76eebb86b05c)

2. Set a Name: `My-EC2-Instance`.
4. Choose an Amazon Machine Image (AMI): 
   - **RedHat Linux** (Preferred for AWS DevOps learning)
5. Choose an Instance Type: 
   - **t2.micro** (Free-tier eligible)
6. Create or Select a Key Pair:
   - Create a new key pair: `aws-key-demo.pem`

     ![image](https://github.com/user-attachments/assets/4a3a1b21-5317-44b4-b20e-d89d21cd56f7)

   - **Download and store it safely**.
7. Configure Security Group:
   - **Allow SSH (port 22)**
   - **Allow HTTP (port 80)** (For web hosting)

     ![image](https://github.com/user-attachments/assets/9cc2e37c-d0e3-491d-876b-34184c8a94f5)

8. Click **Launch Instance**.

   ![image](https://github.com/user-attachments/assets/a9475e2d-3bb4-4c75-9a61-1d9af69689a4)

### **✅ Solution 2: Installation of Web Server**

#### **For Apache (RedHat/CentOS):**
```
sudo yum install httpd -y
sudo systemctl start httpd
sudo systemctl enable httpd
```

**Then, restart the server:**
```
sudo systemctl restart httpd
```

![Screenshot 2025-02-13 145245](https://github.com/user-attachments/assets/d50efb2a-dace-4b4d-9ef4-8a9a3bf68c5c)


#### **✅ **Step 3: Running SSH in Git Bash**
1. Open **Git Bash**  
2. Navigate to the key folder:
   ```
   cd /d/AWS/Final\ Job
   ```

   ![Screenshot 2025-02-13 145257](https://github.com/user-attachments/assets/e40cbc39-5330-480a-8393-a1d8fa5ea731)

4. Run:
   ```
   ssh -i aws-key.pem ec2-user@YOUR_PUBLIC_IP
   ```
You're getting the error:  

```bash
-bash: cd: /var/www/html/index.html: No such file or directory
```

This happens because `index.html` is a **file**, not a directory. The `cd` (change directory) command is only used to navigate into **directories**, not files.  

---

### **✅ Solution 4: Create a HTML web page**
Instead of running:
```
cd /var/www/html
```

**Create an `index.html` file:**
```
vi index.html
```

**Add some basic HTML:**
```
<!DOCTYPE html>
<html>
<head><title>Welcome</title></head>
<body><h1>Hello, AWS!</h1></body>
</html>
```

![Screenshot 2025-02-13 145314](https://github.com/user-attachments/assets/69fda91f-dffe-4752-b082-2fb53f12309c)

![Screenshot 2025-02-13 145400](https://github.com/user-attachments/assets/9607b1ec-884d-4425-ad96-13cebd04ca05)

**Press :wq! to save and quit.**

---

### **✅ Solution 5:**Test the web-server is running or not**
```

http://<EC2 public-ip address>
```


## 4️⃣ Final Output 🎉

![Screenshot 2025-02-13 144914](https://github.com/user-attachments/assets/0a598523-974a-4a43-9409-0aa61b2aebe5)

#### ✅ Successfully Launched EC2 Instance
#### ✅ Successfully Connected to EC2 via SSH
#### ✅ Hosted a Web Page on EC2 (Accessible via Public IP)

#### 🔥 Hands-on Tasks (To Complete)
#### ✅ Launch a RedHat EC2 instance
#### ✅ Connect via SSH
#### ✅ Install & start Apache Web Server 
#### ✅ Configure Security Groups for HTTP traffic 
#### ✅ Automate setup with User Data script 


🚀 **EC2 Setup Completed Successfully!** 🎉

---
