## Project Title: Apache HTTP Web Server Installation on CentOS 8

### Project Description:

 This project aims to provide a step-by-step guide on installing and configuring an Apache HTTP web server on a CentOS 8 server. It will cover the essential steps involved, from package installation and configuration to testing and verification.

![apache](https://github.com/owootomo/Devops-Project/assets/144632027/24702ea8-2b89-4849-baac-96ea37aee152)

![1_D41zkHpHH0qWe7B8Z4sLZw](https://github.com/owootomo/Devops-Project/assets/144632027/317e9e89-0795-42ab-a250-574cc2ab363f)

## CentOS 8: A Reliable and Robust Linux Distribution

CentOS 8 is a leading open-source Linux distribution renowned for its stability, security, and enterprise-grade capabilities. It is widely adopted by organizations seeking a dependable platform for their IT infrastructure. CentOS 8 offers a range of benefits that make it an attractive choice for both personal and professional use.

### Key Advantages of CentOS 8:

Enhanced Performance: CentOS 8 boasts improved performance compared to its predecessors, delivering faster boot times, reduced latency, and overall system responsiveness.

Stable API: CentOS 8 maintains a stable Application Programming Interface (API), ensuring compatibility with existing software and applications. This stability minimizes disruptions and simplifies software management.

Large File Support: CentOS 8 introduces support for packaging files larger than 4GB, addressing limitations encountered in previous versions. This enhanced support facilitates the deployment of large-scale applications and data files.

## Apache HTTP: A Pillar of Web Server Technology

Apache HTTP, often referred to as simply Apache stands as a cornerstone of web server technology. Its widespread adoption, spanning over 30% of all known websites, can be attributed to its versatility, compatibility, and robust feature set.

### Essential Role of Apache HTTP:

Client-Server Communication: Apache HTTP serves as a mediator between web servers and user browsers, enabling seamless data exchange.

Content Delivery: Apache HTTP efficiently retrieves and delivers web content, including HTML pages, images, and other multimedia resources.

Platform Agnosticism: Apache HTTP's compatibility with various operating systems, including Unix, Linux, and Windows, contributes to its extensive adoption.

### Prerequisites

Before embarking on the Apache web server installation process, I ensure that the following prerequisites are met:

 ## 1. Non-Root User with Sudo Privileges:

A non-root user account with sudo privileges is required to perform administrative tasks without compromising the security of the root account.
Ensure that sudo privileges are correctly configured for the non-root user.
Up-to-Date System Packages:

Maintain the system's integrity and security by updating all packages before installation and executing the command _sudo yum update_ to refresh the package database and install available updates.
I enter the password when prompted to initiate the update process. Once these prerequisites are fulfilled, I can proceed with the installation of the Apache web server.
![sudo yum](https://github.com/owootomo/Devops-Project/assets/144632027/6ff78601-94f1-4237-afa4-f6dc9341e666)

 ## 2. Install the Apache HTTP web server using the command sudo dnf install httpd.
![apache2](https://github.com/owootomo/Devops-Project/assets/144632027/4e2e01ee-d1fc-425c-afdb-dce1d2fc7bd3)

## 3. Step 3 — Enable and start the Apache service

To enable the Apache server I  will enter the command sudo systemctl enable httpd.service, and will then be prompted to enter your password again. I will enter password to complete Apache enabling.

Quick Note: To verify that the server is indeed up and running, we enter the command sudo systemctl status httpd.service, and should see an active status to let you know the Apache software is currently active/running.

![verified](https://github.com/owootomo/Devops-Project/assets/144632027/72967150-d037-49ea-a038-931e689d0c6a)

## 4. Step 4 - Open the firewall for HTTP

Finally, let's open the firewall to allow access to the web server. Firewalls serve as a crucial layer of security for your server by blocking traffic to all ports except those you explicitly permit. Since we're setting up a firewall for HTTP server functionality, execute the following command:

```
sudo firewall-cmd --permanent --add-service=http
```
on the screen should now resemble the following:

Success:
-- firewalld service "http" has been added.
This indicates that the firewall has successfully granted access to the HTTP service.

With the firewall configured, it's time to see if our Apache server is up and running! To do this, I will grab the server's public IP address and paste it into my web browser's address bar. If everything goes smoothly, I should be greeted with the default Apache test page, signifying a successful Apache HTTP web server installation on your CentOS 8 server! Congratulations! 


![httpserver](https://github.com/owootomo/Devops-Project/assets/144632027/e91c3e2e-4a4d-47d2-b11b-7a9e656a2e36)

