# 🔐 AWS IAM Project – Secure Cloud Access for Teams

In this project, we leverage **AWS Identity and Access Management (IAM)** to securely manage **access control**, user roles, and permissions for EC2 instances.

📍 **Goal**: Onboard an intern to a company AWS environment (NextWork) with *just enough* access to perform tasks on EC2 resources — securely and efficiently.

---

## 📚 What You Will Learn

- How to create and manage **IAM users**, **user groups**, and **policies**
- How to assign **least-privilege access** to EC2 instances
- How to use **account aliases** for easier login
- How to enforce permission boundaries using IAM **policies with conditions**

---

## 🧠 Scenario

> 👩‍💻 **You are onboarding a new intern at your company.**  
> They need controlled access to EC2 instances in the `development` environment — not production.

---

## 💻 EC2 Instances

You'll work with two EC2 instances tagged under different environments:

- **Production**
- **Development**

📸 *EC2 Dashboard View*  
![EC2](https://github.com/user-attachments/assets/47317445-2ed5-496c-a146-83976399dd47)

---

## 📜 IAM Policy

> 🔐 This custom IAM policy allows access to EC2 resources *only* tagged as `Env: development`, provides read-only `Describe` access, and denies tag modifications.

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": "ec2:*",
      "Resource": "*",
      "Condition": {
        "StringEquals": {
          "ec2:ResourceTag/Env": "development"
        }
      }
    },
    {
      "Effect": "Allow",
      "Action": "ec2:Describe*",
      "Resource": "*"
    },
    {
      "Effect": "Deny",
      "Action": [
        "ec2:DeleteTags",
        "ec2:CreateTags"
      ],
      "Resource": "*"
    }
  ]
}
```
we'll be using the AWS Identity and Access Management (IAM) service to control who is authenticated (signed in) and authorized (has permissions) in your AWS console.
![image](https://github.com/user-attachments/assets/4ec112ce-9949-4968-88eb-7a4ca5bdc7f9)
# 📸 Policy Attachments View
![image](https://github.com/user-attachments/assets/9b4e7956-3dd3-4f2e-bac3-811d4d533d42)
# 👩‍👩‍👧 IAM Users and User Groups
- Create a new User Group
- Attach the custom policy to the group
- Add the intern as a new IAM User to this group
 📸 User & Group Creation Steps
![image](https://github.com/user-attachments/assets/9cbf2a96-83ea-4901-aa8a-aa0e481eb33a)
![image](https://github.com/user-attachments/assets/f1806936-d18b-4080-88d8-d0f9ef95a239)
# 🔖 AWS Account Alias
- Replace the numeric AWS account sign-in link with a readable alias:
- Default Sign-in:
`` https://<account-id>.signin.aws.amazon.com/console/``
- Friendly Sign-in:
`` https://<your-alias>.signin.aws.amazon.com/console/``
📸 Alias Setup Screenshot
![image](https://github.com/user-attachments/assets/fb543975-9bb8-4a75-8c8b-9322a128ed9d)
🔐 Login to AWS as Intern
- Use Incognito mode or private tab
- Log in with your newly created user via alias URL
📸 Login View
![image](https://github.com/user-attachments/assets/0dc8be5d-1a28-4d4e-8e88-0acd09191a47)

# ✅ Testing Access: EC2 Instance Actions
- Go to EC2 Console
- Make sure you're in the correct Region
- Try starting/stopping different instances:

- ``✅ Allowed: development-tagged instances``
- ``❌ Blocked: production-tagged instances``
- 📸 Testing Access Screenshot
![image](https://github.com/user-attachments/assets/ad8c06ed-b3db-4d20-ab5f-4a84335f7bc5)
# 🔍 Observed: Access Denied for Production Instance
![image](https://github.com/user-attachments/assets/5cb5bd89-b300-46d9-88d8-498b4469e9dd)
🧹 Resource Cleanup
- Once you're done testing, make sure to clean up:
- EC2 Instances
- IAM Users & Groups
- Custom Policies
![image](https://github.com/user-attachments/assets/1fea160a-8984-426c-a3e9-0c9877d29a47)
# 🧠 Key Concepts Covered
| Feature          | Description                                                    |
| ---------------- | -------------------------------------------------------------- |
| IAM Policy       | Defines permissions (Allow/Deny) on AWS resources              |
| Resource Tagging | Enables fine-grained access control (e.g., `Env: development`) |
| User Groups      | Easily assign policies to multiple users                       |
| Account Alias    | Simplifies sign-in process for IAM users                       |
| Condition Keys   | Controls when/where permissions apply                          |

# 🙌 Credits
Project inspired by AWS IAM best practices and tailored for secure team onboarding in a cloud environment.
# 📎 Resources
- AWS IAM Docs
- Create IAM Policies
- EC2 Tag-based Access Control
# 🔗 Related Projects
- AWS S3 Bucket Replication (CRR)
- Docker + MongoDB Practice (Coming soon)

# 🚀 Follow My Cloud Journey
I'm learning AWS hands-on to become a Cloud Engineer.
This project is part of my daily grind — follow me on GitHub and LinkedIn for more!





