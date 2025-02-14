# How to Select "Programmatic Access" for an IAM User

## 🚀 **Steps to Enable Programmatic Access for an IAM User (AWS Console)**

### 1️⃣ **Go to AWS IAM Console**
- Open **AWS Management Console**
- Search for **IAM** in the AWS search bar and open it.

### 2️⃣ **Create a New User**
- Click **Users** on the left sidebar.
- Click **Add User** (blue button).

### 3️⃣ **Enter User Details**
- **User name:** Enter a username (e.g., `aws-admin`).
- **Select Access Type:**
  ✅ **Check the box** for **Programmatic access** (CLI, SDK, API access).
  ✅ This will generate **Access Key ID** & **Secret Access Key** (needed for CLI).

### 4️⃣ **Click "Next: Permissions"** and proceed with group and policy setup.

### 5️⃣ **Complete the Setup**
- After adding permissions, click **Next → Review → Create User**.
- You will now see the **Access Key ID & Secret Key**.
- **Download the .csv file** for future use (you cannot retrieve it later).

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
```powershell
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

### **Step 3: Verify Login by Running AWS CLI Commands**  
Test if everything is working with:  
```powershell
aws s3 ls
```
If your IAM user has access to S3, this will list your S3 buckets.  

Another test command:  
```powershell
aws ec2 describe-instances
```
If you get a **valid JSON response**, your AWS CLI is successfully authenticated! 🚀  

---

### **Step 4: Optional - Set Up AWS CLI Profile (For Multiple Users)**  
If you need to manage multiple AWS accounts, use profiles:  
```powershell
aws configure --profile myprofile
```
Then, use it in commands:  
```powershell
aws s3 ls --profile myprofile
```

---

### **Next Step:**  
Now that AWS CLI is set up, **let's continue with IAM hands-on tasks!**  
Let me know if you face any issues! 🔥🚀  

🔗 **Additional Resources:**
📘 [AWS IAM Documentation](https://docs.aws.amazon.com/IAM/latest/UserGuide/)  
📘 [AWS CLI Configuration Guide](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-files.html)  

Let me know if you need further clarification! 🔥
