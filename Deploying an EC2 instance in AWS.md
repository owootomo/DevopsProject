## Deploying an EC2 Instance in AWS and Install an Apache Web Server with a BASH Script

# MISSION
Our company wants to start shifting from using on-premises servers to using servers in the cloud. Instead of purchasing all the infrastructure in a data center, they have asked me to create an EC2 instance in AWS to host their new website. Follow along as I guide us through this mission safe and sound!
![aws](https://github.com/owootomo/Devops-Project/assets/144632027/993be7bb-e00b-49cd-b6d2-ef72d308b659)

I may be familiar with AWS (Amazon Web Services) because pretty much everyone utilizes the online shopping powerhouse in today’s market. However, AWS is far more than an online shopping platform. Amazon Web Services is a cloud service provider that supplies a variety of computing services that are made accessible via the internet. The beauty of AWS is that the software makes for easy management and maintenance of hardware and infrastructure, which saves organizations and individuals the cost and headache of buying and operating resources on-site. Additionally, these resources can be utilized for free or on a pay-per-use basis. Can't beat that, right?

## What are EC2 Instances?

![ec2](https://github.com/owootomo/Devops-Project/assets/144632027/975f250e-5796-4107-8078-a861f7565c58)
EC2 or Elastic Compute Cloud is a software that allows me to rent and manage virtual servers in the cloud. So the EC2 Instances are virtual servers located within Amazon’s Elastic Compute Cloud (EC2) for running applications on the AWS infrastructure.

Now that I have the base understanding of the two, let's dive in!

* Prerequisites
* AWS Account
* Understanding of Linux Fundamentals
* Terminal Access

# Step 1 — Create AWS Account
I'll want to be sure to set up my AWS root user account. Click the link to do so. Once my account is created, I'll be inside my AWS management console, which is where I will then create my IAM User Account. It is important to note that my root account is not meant to be used for day-to-day operations. This is why the IAM User account needs to be created.

[Click here to go to AWS Sign-In and Billing Signup](https://signin.aws.amazon.com/signin?redirect_uri=https%3A%2F%2Fportal.aws.amazon.com%2Fbilling%2Fsignup%2Fresume&client_id=signup&code_challenge_method=SHA-256&code_challenge=ERxLjcpDRUeXhhYzle3RS8m-KWWSyjK_gLxvOT6Xh6U#/start/email)

# Step 2: Establishing Your IAM User Account

Within the AWS management console, initiate the creation of my IAM User account. 

* Go to your name on the top right and select _Security Credentials_

* 1: Access the AWS Management Console
Open your web browser and navigate to the AWS Management Console.
Sign in with your AWS account credentials.
* 2: Navigate to IAM
Once logged in, find and select the "Services" dropdown in the top left corner.
Under the "Security, Identity, & Compliance" section, choose "IAM" (Identity and Access Management).
* 3: Access IAM Dashboard
In the IAM console, select "Users" from the left-hand navigation pane.
This will take you to the "Users" dashboard, where you can manage IAM users.
* 4: Add a New IAM User
Click the "Add user" button.
Enter a username for the new IAM user.
Choose the type of access - either programmatic access, AWS Management Console access, or both.
* 5: Set Permissions
In the permissions configuration step, you can attach policies. Click "Attach policies."
In the filter policies search box, type "ElementalApplianceSoftwareFullAccess."
Select the policy from the list.
Click "Next: Tags" if you want to add tags (optional).
* 6: Review and Create
Review your choices on the summary page.
Click "Create user" to finish the process.
* 7: Access Credentials
Once the user is created, you'll see a confirmation page.

Once this process is finalized, I will share a screenshot with the users. Upon creating the link, they will be directed to the login screen where they'll be prompted to set a new password. Following this, they will gain access to the account according to the policy applied. 
The newly created user will then be visible under the user section in our account.


# Step 3, I will launch an EC2 instance in AWS. 
From my AWS Management Console, I will type in "EC2" in the search bar to access the EC2 dashboard. Next, I will click the orange "Launch Instance" button to initiate the launch process.









