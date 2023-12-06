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

# Step 1:  Create AWS Account
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


# Step 3: I will launch an EC2 instance in AWS. 
From my AWS Management Console, I will type in "EC2" in the search bar to access the EC2 dashboard. Next, I will click the orange "Launch Instance" button to initiate the launch process.

On the "Launch An Instance" interface, designate a name (Feel free to choose any name; I'll use 'nayawebserver' as an example) for your virtual web server and choose an Amazon Machine Image (AMI) with a t2.micro Instance Type. For this task, we'll opt for the Amazon Linux AMI to accomplish our objectives.

<img width="675" alt="image" src="https://github.com/owootomo/Devops-Project/assets/144632027/b5e0ec91-a895-4d57-9041-4cf077849ad5">

<img width="581" alt="image" src="https://github.com/owootomo/Devops-Project/assets/144632027/6031bc7d-166b-4fb6-a821-0d826a787c4b">

After choosing the instance type, it is necessary to generate a new key pair, enabling us to establish a secure connection to our instance.

<img width="576" alt="image" src="https://github.com/owootomo/Devops-Project/assets/144632027/de85eebb-3bf9-4aa2-b7bf-f55982b508c4">

Click the Create a new key pair button

I already created a Key Paid so when I drop down, it shows my current KeyPair as seen below
<img width="586" alt="image" src="https://github.com/owootomo/Devops-Project/assets/144632027/0a81f58f-dd5d-4a1c-b083-5d4e937da307">

Next, it's essential to configure the appropriate firewall settings. In line with the mission requirements, we are tasked with establishing a security group permitting inbound traffic on HTTP for 0.0.0.0/0 and inbound traffic on SSH specifically from your IP address. To achieve this, we will set up our configurations as outlined below.

<img width="583" alt="image" src="https://github.com/owootomo/Devops-Project/assets/144632027/f2f9623e-0311-4030-ade1-dda2b2cdeb4f">

Once we have our settings in place, we can click Launch Instance to get it up and running.

<img width="286" alt="image" src="https://github.com/owootomo/Devops-Project/assets/144632027/ef5e401f-82bb-495d-bdb9-02e310ad3be2">


On the subsequent screen, a green box should indicate the successful launch. Click on "View All Instances" to navigate to the Instances screen. It might take a moment, but once the instance state displays "running," that signals your cue to proceed, signifying that the instance is now ready for use!

![image](https://github.com/owootomo/Devops-Project/assets/144632027/9146b469-9b9f-4837-b1e9-9881c0433eb9)

# Step 4: Connect to your EC2 instance via SSH and install Apache, along with a customized webpage, using a BASH script.

<img width="939" alt="image" src="https://github.com/owootomo/Devops-Project/assets/144632027/822cd6cb-4cb9-443c-9ecf-dc9e5269a0ab">

Instance State status must read “Running” before connecting

<img width="607" alt="image" src="https://github.com/owootomo/Devops-Project/assets/144632027/5de6e867-959f-4a9c-94bd-e3c24e6bd41c">

Click Connect to launch terminal

The displayed screen below confirms your successful login.

<img width="554" alt="image" src="https://github.com/owootomo/Devops-Project/assets/144632027/c06b2f0e-a8e6-43b4-b455-a2171f8d3c3e">

Now, let's conclude by installing Apache along with a custom webpage through a BASH script. Before proceeding with the Apache installation, let's apply the recommended updates as advised by the EC2 terminal. Use the following command:

```
sudo yum update
```

## File Creation:
Begin by creating the file for our BASH script, and then employ the VIM command to enter and create the script within the same file. Utilize the commands provided below:
<img width="312" alt="image" src="https://github.com/owootomo/Devops-Project/assets/144632027/661500f3-a3fe-4ca1-8ebd-17be05359047">

Next, let's utilize VIM. The commands should appear as follows. The text on line 6 should contain customized content that will be displayed upon the completion of this entire process. Save the VIM by using:wq after entering the code.
<img width="568" alt="image" src="https://github.com/owootomo/Devops-Project/assets/144632027/26398532-3261-4be6-afbc-6e69e06ca812">

We must now grant execute permissions to our file and execute it. The provided commands will walk you through this process. After running these commands, the final step is to paste your IP address into your web browser.

<img width="374" alt="image" src="https://github.com/owootomo/Devops-Project/assets/144632027/050aaa62-88d8-4257-bdb6-d2abaaac2b01">

<img width="316" alt="image" src="https://github.com/owootomo/Devops-Project/assets/144632027/6617b9b9-1466-43e6-b576-b66adb2a7d3c">

<img width="1097" alt="image" src="https://github.com/owootomo/Devops-Project/assets/144632027/dc4af3fc-c375-44ef-b258-91a3ea59bad8">

Finally! We have effectively deployed an EC2 instance in AWS and installed Apache using a BASH script.




















