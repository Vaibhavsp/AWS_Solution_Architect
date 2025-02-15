# Hands-on AWS IAM with step-by-step solutions for common errors.

### 1️⃣ **Go to AWS IAM Console**
- Open **AWS Management Console**
- Search for **IAM** in the AWS search bar and open it.

  ![1](https://github.com/user-attachments/assets/5c3d29c5-f1eb-4a1e-8a03-92e83f286247)


### 2️⃣ **Create a New User**
- Click **Users** on the left sidebar.

  ![2](https://github.com/user-attachments/assets/9836b7ad-24eb-4d94-bbc5-042ec957eae4)

- Click **Create User** (blue button).

![3](https://github.com/user-attachments/assets/e6e2bd0d-324c-4fbe-bf85-9dca51723b11)

### 3️⃣ **Enter User Details**
- **User name:** Enter a username (e.g., `aws-admin`).

  ![5](https://github.com/user-attachments/assets/ec1102ab-eb8b-4711-adc8-a3b787aff2e3)

- **Create a IAM Group:**

  ![6](https://github.com/user-attachments/assets/11112243-c735-46d1-ae99-6dbe78567075)

- **Attach the Policies to the Group:**

![7](https://github.com/user-attachments/assets/77f53ae2-a315-4618-b381-2ea234e1f677)

- **Attach the Policies to the User:**

![8](https://github.com/user-attachments/assets/e10d15aa-0990-4865-87e8-72b9e69035f8)

![9](https://github.com/user-attachments/assets/141f33c2-bfab-4d95-a682-f88012c3747a)

![10](https://github.com/user-attachments/assets/f2708199-c032-40ee-a758-f83efaae958e)

- **IAM Created:**
  
![11](https://github.com/user-attachments/assets/70140804-1311-4bd7-9172-c2da8e1f646f)

- **IAM User Policies:**

  ![12](https://github.com/user-attachments/assets/00a85f8d-24be-4860-b08c-c5f8d4af3695)

- **Select Access Type:**
  ✅ **Check the box** for **Programmatic access** (CLI, SDK, API access).

  ![13](https://github.com/user-attachments/assets/7e970454-4b90-4bf5-ac6e-58ab1ca55998)

  ✅ This will generate **Access Key ID** & **Secret Access Key** (needed for CLI).

![14](https://github.com/user-attachments/assets/15eaec74-44f0-46b3-b5d3-03333441d5f0)

### 4️⃣ **Click "Next: Permissions"** and proceed with group and policy setup.

### 5️⃣ **Complete the Setup**
- After adding permissions, click **Next → Review → Create User**.
- You will now see the **Access Key ID & Secret Key**.
- **Download the .csv file** for future use (you cannot retrieve it later).

  ![15](https://github.com/user-attachments/assets/df9cf3c7-5a16-4c16-a31d-059dc73bfe63)

---

## 🔹 **How to Verify Programmatic Access?**
After creating the user, test access using AWS CLI:
```bash
aws configure
```
- **Enter Access Key ID**
- **Enter Secret Access Key**
- **Select Region (e.g., ap-south-1 for Mumbai)**
- **Output format:** json

✅ Now, you can use the AWS CLI with the new IAM user! 🚀

---

## **How to Log in to AWS CLI on Windows PowerShell**  

Follow these steps to set up and log in to AWS CLI on Windows PowerShell:  

### **Step 1: Install AWS CLI on Windows**  
If you haven't installed AWS CLI yet, download and install it:  
🔹 **Download AWS CLI for Windows** 👉 [Click Here](https://awscli.amazonaws.com/AWSCLIV2.msi)  

✅ **After installation, verify the installation:**  
Open PowerShell and run:  
```
aws --version
```
📌 **Expected Output:**  
```
aws-cli/2.x.x Python/x.x.x Windows/x.x
```

---

### **Step 2: Configure AWS CLI with IAM Credentials**  
1️⃣ **Open PowerShell**  
2️⃣ **Run the following command:**  
```powershell
aws configure
```
3️⃣ **Enter the IAM credentials (from the .csv file you downloaded):**  
   - **AWS Access Key ID:** `AKIAXXXXXX`  
   - **AWS Secret Access Key:** `XXXXXX/XXXXXX`  
   - **Default region name:** `ap-south-1` (for Mumbai)  
   - **Default output format:** `json` (or leave blank for default)  

✅ **Now AWS CLI is configured and ready to use!**  

---

### **Step 4: Create an IAM User via AWS CLI**
🔹 **Create User**  
```
aws iam create-user --user-name aws-admin
```

🔹 **Create Access Key** (for CLI login)  
```
aws iam create-access-key --user-name aws-admin
```

🔹 **Create Group & Attach Policy**  
```
aws iam create-group --group-name AdminGroup
aws iam attach-group-policy --group-name AdminGroup --policy-arn arn:aws:iam::aws:policy/AdministratorAccess
```

🔹 **Add User to Group**  
```
aws iam add-user-to-group --user-name aws-admin --group-name AdminGroup
```

![21](https://github.com/user-attachments/assets/525fdbdc-0885-483a-b134-1fb18c2964ac)

![22](https://github.com/user-attachments/assets/aaefc764-2db0-4b6a-a56b-583f23048de1)

🔹 **IAM User and IAM Group Created by CLI**  
![18](https://github.com/user-attachments/assets/220cd62f-fe0f-4978-8397-22b07e6f0c37)

![19](https://github.com/user-attachments/assets/781d68b0-245c-47b4-af52-b8ae62bca9ab)

![20](https://github.com/user-attachments/assets/76335a67-7d71-4af8-a9e5-1c8158900819)

---

## **🔥 Day 2: IAM Roles, MFA, and Security Best Practices**
### **Step 5: Create an IAM Role (AWS Console)**
1️⃣ Go to **IAM → Roles → Create Role** 

![23](https://github.com/user-attachments/assets/a2baa252-d8e5-4b51-a954-741014405a8e)

2️⃣ Select **AWS Service** → Choose **EC2**  
3️⃣ Click **Next → Attach Policies** 

![24](https://github.com/user-attachments/assets/d8d360b1-aca4-45bc-8772-90321a240caa)

4️⃣ Attach **AmazonS3FullAccess** (For S3 access from EC2)

![25](https://github.com/user-attachments/assets/bac12da1-84fc-4af0-8581-8ffbb0fde158)

5️⃣ Click **Next → Create Role**  

![26](https://github.com/user-attachments/assets/143f685f-82c4-473b-a76a-2b6585d98ff2)

6️⃣ Assign this role to an **EC2 instance**  

![27](https://github.com/user-attachments/assets/149035e7-5a2b-4f02-a122-e91ef2610878)

![28](https://github.com/user-attachments/assets/130457fc-a21e-4410-8936-b923f5ed3fca)


✅ Now, EC2 can access S3 **without storing AWS keys!**  

---

### **Step 6: Enable Multi-Factor Authentication (MFA)**
1️⃣ Go to **IAM → Users → Your User → Security Credentials**  
2️⃣ Click **Activate MFA** → Choose **Virtual MFA Device**  
3️⃣ Use **Google Authenticator App** (Scan the QR Code)  
4️⃣ Enter 2 MFA codes & Click **Enable MFA**  

✅ **Now, AWS login requires both Password & MFA Code!**  

---

### **Step 7: Best Practices for IAM Security**
🔹 **DO NOT use the root account** for daily tasks  
🔹 **Enable MFA** for all users  
🔹 **Use IAM Roles** instead of hardcoding access keys  
🔹 **Apply the Least Privilege Principle** (Give minimum required access)  
🔹 **Rotate Access Keys** regularly  

---

## **✅ What’s Next?**
Next up is **Amazon VPC (Networking Essentials)!** 🌐🔥  
Let me know if you have any questions before we proceed! 🚀
🔗 **Additional Resources:**
📘 [AWS IAM Documentation](https://docs.aws.amazon.com/IAM/latest/UserGuide/)  
📘 [AWS CLI Configuration Guide](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-files.html)  

Let me know if you need further clarification! 🔥
