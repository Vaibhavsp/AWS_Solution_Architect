# IAM Roles and the Employee Directory Application

## 🔹 **Introduction**
IAM roles allow AWS services and applications to securely access AWS resources without requiring long-term credentials. This document explains how IAM roles enable the **Employee Directory Application** to interact with AWS services securely.

---

## 🏢 **How IAM Roles Work with the Employee Directory Application**
### 🔑 **Key Concepts:**
1. **IAM Roles for EC2 Instances**
   - IAM roles provide temporary credentials.
   - Credentials are automatically rotated via the instance profile.
   - No need for storing static AWS credentials in the application.

2. **AWS SDK and IAM Roles**
   - AWS SDK automatically retrieves and refreshes temporary credentials.
   - Ensures secure API calls to AWS services like **Amazon S3** and **Amazon DynamoDB**.

---

## 🔹 **IAM Role Implementation in Employee Directory App**
### 📌 **IAM Role: EmployeeWebApp**
- **Used in AWS IAM Demo**
- Policies attached:
  - `AmazonS3FullAccess`
  - `AmazonDynamoDBFullAccess`

### 📌 **IAM Role: S3DynamoDBFullAccessRole**
- **Used in later demos for EC2 Instance Configuration**
- Grants the same permissions as **EmployeeWebApp** role.

✅ **Best Practice:** Assign only the required permissions to IAM roles to follow the principle of **least privilege**.

---

## 📌 **Hosting the Employee Directory Application on AWS**
- Uses **Amazon EC2** for compute power.
- Uses **Amazon VPC** for secure networking.
- IAM roles provide **temporary credentials** for AWS API access.

### 🔹 **Next Steps for Implementation**
1. **Watch IAM Role Setup Demo** to understand how to create and assign roles.
2. **Review Application Hosting Demo** before configuring your own EC2 instance.
3. **Follow step-by-step IAM role creation exercises** in upcoming training sessions.

---

## 🔑 **Key Takeaways**
✅ IAM roles eliminate the need for long-term credentials.
✅ Automatically rotates credentials for security.
✅ Used by AWS services like **EC2, Lambda, and S3**.
✅ Ensures applications securely authenticate AWS API calls.

🔗 **Additional Resources:**
📘 [AWS IAM Documentation](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles.html)  
📘 [AWS EC2 IAM Roles](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/iam-roles-for-amazon-ec2.html)  

🚀 *Use IAM roles to secure AWS applications efficiently!*

