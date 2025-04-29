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

# Create IAM Users and User Groups:

![image](https://github.com/user-attachments/assets/78fe72b6-83c7-4824-8feb-9514b2f31d92)

#  add Users to your user group:

![image](https://github.com/user-attachments/assets/0abefd98-4eea-4bfc-a72c-e007339d7bc5)

# LOGIN IN TO ALIAS ACC VIA PRIVATE TAB:

![image](https://github.com/user-attachments/assets/c9457ea3-f706-461a-982e-876cac897e57)

Head to your EC2 console, and make sure you're in the same Region as the one where you deployed your two production and development instances.
Head to Instances.
Select your production instance, and in the Actions dropdown, select Manage instance state.

![image](https://github.com/user-attachments/assets/811ebbc6-a9be-4a30-993e-5404c0fd539b)

# instance stopped bcoz the user has access to EC2 Service :

![image](https://github.com/user-attachments/assets/fcf605a2-0eca-41a3-be07-48b30ee59e9f)


# DELETE RESOURCES :

![image](https://github.com/user-attachments/assets/de2b0518-1ce2-404a-b4b6-223ab120c60c)







