## Step 1 – Setting Up the NGINX Web Server
To deliver web content to our visitors, I will leverage NGINX, a high-performance web server. Let's kick off by using the apt package manager for installation.  Then, install Nginx using the following commands:

```
sudo apt update
sudo apt install nginx
```

When prompted, confirm the installation by entering 'Y'. Once installed, the Nginx web server will be up and running on the Ubuntu 20.04 server.

To verify the successful installation and the active status of Nginx, run:

```
sudo systemctl status nginx
```
If the status is green and indicates that Nginx is running, Then I have just deployed my Web Server in the Cloud!

Before my Web Server can receive traffic, I will need to open TCP port 80, the default port used by web browsers to access web pages on the internet.

Given that I already have TCP port 22 open for SSH access by default on our EC2 machine, I will add a rule to the EC2 configuration to allow inbound connections through port 80

<img width="307" alt="image" src="https://github.com/owootomo/Devops-Project/assets/144632027/9f69e2e7-f4fa-45fc-be69-267e7376a6eb">

Our server is now running, accessible both locally and from the internet (Source 0.0.0.0/0 means 'from any IP address').

First, let's check how we can access it locally in our Ubuntu shell using the following commands:
```
curl http://localhost:80
or
curl http://127.0.0.1:80
```

Both commands essentially do the same thing – they use the 'curl' command to request the Nginx on port 80. The difference lies in trying to access the server via DNS name in the first case and by IP address in the second. As an output, we'll see some oddly formatted text – don't worry, it simply confirms that the Nginx web service responds to the 'curl' command with some payload.

Open your preferred web browser and try accessing the following URL:
```
http://<Public-IP-Address>:80
```

To retrieve my Public IP address, I will use the following command:

```
curl -s http://169.254.169.254/latest/meta-data/public-ipv4
```

The URL in the browser should also work without specifying the port number since web browsers default to port 80.
<img width="307" alt="image" src="https://github.com/owootomo/Devops-Project/assets/144632027/d6bfc832-8ae4-4361-b3e7-f2b7d755a647">

This page essentially mirrors the content obtained through the 'curl' command but is nicely formatted in HTML by your web browser. Now, my NGINX web server is up and running.

