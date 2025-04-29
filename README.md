# AWS-IAM-PROJECT
we'll be using the AWS Identity and Access Management (IAM) service to control who is authenticated (signed in) and authorized (has permissions) in your AWS console.

![image](https://github.com/user-attachments/assets/4ec112ce-9949-4968-88eb-7a4ca5bdc7f9)

💻 EC2 instances

📏 IAM Policies

👩‍👩‍👧‍👧 IAM Users and User Groups

🔖 AWS Account Alias

# Scenario:
👩‍💻 Onboard an intern working at NextWork - they should have the right permission settings to contribute while keeping the company's resources secure.

# EC2 - INSTANCE
![image](https://github.com/user-attachments/assets/47317445-2ed5-496c-a146-83976399dd47)

# IAM Policy:
💡 What is a Policy?
An IAM policy is a rule for who can do what with your AWS resources. It's all about giving permissions to IAM users, groups, or roles, saying what they can or can't do on certain resources, and when those rules kick in.

# JSON FILE :


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

![image](https://github.com/user-attachments/assets/b121a802-d484-44fb-8f8a-6a8fb145f5b4)


![image](https://github.com/user-attachments/assets/2ffa8242-a738-4614-813e-3b05abcc83a0)


 #  AWS Account Alias:

 An Account Alias is a friendly name for your AWS account that you can use instead of your account ID (which is usually a bunch of digits) to sign in to the AWS Management Console.

Your AWS account's sign-in page has this URL by default: https://Your_Account_ID.signin.aws.amazon.com/console/

If you create an AWS account alias for your AWS account ID, your sign-in page URL looks more like: https://Your_Account_Alias.signin.aws.amazon.com/console/


![image](https://github.com/user-attachments/assets/470755e4-bc7c-415b-ad9d-fa3396c694d6)
