# Altschoolsemester2

# Dynamic Web App Deployment (Azure + Nginx)

This project showcases the deployment of a dynamic web application using modern tools and practices. It involves setting up a cloud-based Ubuntu server, configuring a web server (Nginx), and deploying a simple interactive web application to demonstrate technical skills to potential investors or stakeholders.

 Project Goals

- Provision a virtual machine (VM) using Azure
- Configure a secure and optimized Nginx web server
- Deploy a web application prototype with dynamic features
- Use a reverse proxy setup (bonus)
- Follow production-level practices in deployment


# Provision the Server (Azure)

#  Steps:
1. Log in to your Azure Portal.
2. Go to **Virtual Machines** > **Create** > **Azure Virtual Machine**.
3. Select an **Ubuntu 22.04 LTS** image.
4. Choose:
   - Size: Standard B1s or B1ms (cost-effective)
   - Username: e.g., `altazureuser`
   - Authentication: SSH public key
5. Allow inbound port: SSH (22) and HTTP (80)
6. Download the private key or ensure your public key is saved in `~/.ssh/id_rsa.pub`.
7. Click **Create** and wait for provisioning to complete.



#  Connect to the Server



-i ~/.ssh/your-key.pem oladunniadekoya@ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAACAQDM+2h65lGwY2ZyBFsq6uZopDG2C+lrGmeXXeY8qC2mimLt1OdGk/BrTu6+gKlIFRx0u7/nQvPhgvJp4NbvosgUmvF0N5RvyiVQIYCp9SKXFrNrQwlXDwdKR3b8qMqtUrziIzyetOjC0w9mBcz+3Clc7AygZdAsYHANHLpiBqmjxOn4MwTwpuTrNIJUtjui+tJRTU9y4eYBuP9TxLFvWjY/TF+M0tsoCIQf9sfngUcbW5JAhQwdSG5WFe0dhOs4myujmtHtd8daRHJuYqUdG4gIfdr3oCz+WbV4WbblSQK67Gg/WjZU4bfia+VU8AiRoxKdKUeC10SkUxLNueuVGUHfbsoaAgcpJnHqHEQX2l5xupB0n2coxok5edTInhawg+VplO2XeJTVme2cNGv459yd+Mce/C/y3OuHPauqO7ct5wko+chVTjHvA2YBpRfCrL094LQVNYdk1GfxfaGHBc0JlSuov2Ph5oItpeETkQnXMYeO3cCOX6iq6dfnxpOd48vB36d4b0uF6JjZXyXdYMXC/hYMOKTe4BU7DoQXTKxqBNKk7O3RneWaXx65G5y7LXN7kz3MndKtijh0HdExulw5VXJ3/FBYC0WlMzt/yetfl10doQKGbp6buo8MVmSKs4NTWjVwyZfmTEArUkxPfhzadmJCNOrTfrdYXxYncVVTmQ== oladunni.adekoya.com

   # web server setup
 sudo apt update
sudo apt install nginx -y

Start and Enable Nginx:
sudo systemctl start nginx
sudo systemctl enable nginx

Setup a Reverse Proxy 

# /etc/nginx/sites-available/default
server {
    listen 80;

    server_name your_domain_or_ip;

    location / {
        proxy_pass http://localhost:3000;
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection 'upgrade';
        proxy_set_header Host $host;
        proxy_cache_bypass $http_upgrade;
    }
}

reload Nginx:

# web page 

![image](https://github.com/user-attachments/assets/23a442db-0ece-465c-8090-fed467708859)

![Screen Shot 2025-06-14 at 19 24 33](https://github.com/user-attachments/assets/7b95b831-6a60-43b6-a21e-f0e0df23b747)



   

![Screen Shot 2025-06-14 at 19 23 53](https://github.com/user-attachments/assets/7f4ba637-ead8-4190-96f7-c75d1635149d)

