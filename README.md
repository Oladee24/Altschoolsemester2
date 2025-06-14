# Altschoolsemester2

# Dynamic Web App Deployment (Digitalocean + Nginx)

This project showcases the deployment of a dynamic web application using modern tools and practices. It involves setting up a cloud-based Ubuntu server, configuring a web server (Nginx), and deploying a simple interactive web application to demonstrate technical skills to potential investors or stakeholders.

 ## Table of Contents/Project Goals

- Provision a virtual machine (VM) using Azure
- Configure a secure and optimized Nginx web server
- Deploy a web application prototype with dynamic features
- Use a reverse proxy setup (bonus)
- Follow production-level practices in deployment



# Public Address
You can view the application at: [http://144.126.197.25](http://144.126.197.25)


# 1. Provisioning the Server

1. Create a DigitalOcean Account: 

2. Create a Droplet:
   - Log in to your DigitalOcean account.
   - Click on "Create" and select "Droplets."
   - Choose an Ubuntu distribution (e.g., Ubuntu 20.04 LTS).
   - Select a plan (the Basic plan is generally sufficient for prototyping).
   - Choose a data center region that is closest to your target audience.
   - Select your authentication method (SSH keys are recommended for security).
   - Click "Create Droplet" to launch your server.

3. **Connect to Your Droplet:**
   - Use the SSH key you set up during the Droplet creation.
   - Open your terminal and connect to your Droplet using:
     
 ssh root@144.126.197.25

 
 
# 2. Web Server Setup
Update Package Index:

sudo apt update
Install Nginx:

sudo apt install nginx
Start and Enable Nginx:

sudo systemctl start nginx
sudo systemctl enable nginx
Check Nginx Status:

sudo systemctl status nginx
Open a Browser: Navigate to http://144.126.197.25 to see the default Nginx welcome page.




#3. Dynamic Landing Page
Create an HTML File:

Create a new HTML file: bash sudo nano /var/www/html/index.html
Add the following content to your HTML file:
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>NexusGrid Commerce</title>
  <link rel="stylesheet" href="in.css" />
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gray-900 text-white font-sans min-h-screen flex flex-col items-center justify-center p-6 space-y-10">

  <!-- Header -->
  <header class="text-center animate-fade-in">
    <h1 class="text-4xl md:text-5xl font-bold text-blue-400 mb-2">Adekoya Catherine</h1>
    <p class="text-xl md:text-2xl text-gray-300">Cloud & DevOps Engineer</p>
  </header>

  <!-- Bio Section -->
  <section class="bg-gray-800 p-6 rounded-2xl shadow-xl max-w-3xl w-full animate-slide-up">
    <h3 class="text-xl font-bold text-blue-200 mb-2">About Me</h3>
    <ul class="list-disc list-inside text-gray-300 space-y-1">
      <li>🛠️ <strong>Skills:</strong> Cloud (AWS, GCP), Linux (Ubuntu), Ansible, Git</li>
      <li>💼 <strong>Projects:</strong> Laravel VM Deployment, VPC Configurations, CI/CD Pipelines</li>
      <li>🎓 <strong>Education:</strong> Landmark University, Kwara State; AltSchool Africa – Cloud Engineering Program</li>
    </ul>
  </section>

  <!-- Project Info -->
  <section class="bg-gray-800 p-6 rounded-2xl shadow-xl max-w-3xl w-full animate-slide-up">
    <h2 class="text-2xl font-semibold text-blue-300 mb-2">Project: The Future of NexusGrid Commerce</h2>
    <p class="text-gray-300 mb-4">
      A robust, cloud-native e-commerce ecosystem designed for scalability, speed, and security.
    </p>
    <p class="text-gray-400 italic">
      This project redefines online commerce by integrating microservices, CI/CD pipelines, and cloud-native tooling.
      Built with Kubernetes, APIs, and high-availability architecture—NexusGrid ensures performance at scale.
    </p>
  </section>

  <!-- Skills Section -->
  <section id="skills" class="bg-gray-800 p-6 rounded-2xl shadow-xl max-w-3xl w-full animate-slide-up">
    <h2 class="text-xl font-bold text-blue-200 mb-4">Skills</h2>
    <div class="space-y-4">
      <div class="skill">
        <h3 class="text-sm font-semibold">HTML, CSS</h3>
        <div class="skill-bar"><div class="progress" style="width: 90%"><span>90%</span></div></div>
      </div>
      <div class="skill">
        <h3 class="text-sm font-semibold">Java</h3>
        <div class="skill-bar"><div class="progress" style="width: 85%"><span>85%</span></div></div>
      </div>
      <div class="skill">
        <h3 class="text-sm font-semibold">JavaScript</h3>
        <div class="skill-bar"><div class="progress" style="width: 75%"><span>75%</span></div></div>
      </div>
      <div class="skill">
        <h3 class="text-sm font-semibold">Python</h3>
        <div class="skill-bar"><div class="progress" style="width: 65%"><span>65%</span></div></div>
      </div>
      <div class="skill">
        <h3 class="text-sm font-semibold">CISCO [Networking]</h3>
        <div class="skill-bar"><div class="progress" style="width: 90%"><span>90%</span></div></div>
      </div>
      <div class="skill">
        <h3 class="text-sm font-semibold">Cloud Computing</h3>
        <div class="skill-bar"><div class="progress" style="width: 80%"><span>80%</span></div></div>
      </div>
    </div>

Create a new css file: bash sudo nano /var/www/html/in.css



#4. Networking & Security
Allow HTTP and HTTPS: Make sure your Droplet's firewall allows inbound traffic on port 80 (HTTP) and port 443 (HTTPS).

Secure with Let’s Encrypt SSL (Certbot):

Install Certbot: bash sudo apt install certbot python3-certbot-nginx
Obtain a certificate: bash sudo certbot --nginx
Follow the prompts to configure SSL for your domain or IP.
Verify HTTPS Configuration: Open a browser and navigate to https://144.126.197.25 to ensure that SSL is correctly configured.

submission/finalstps


Initialize a new repository and push your project files, including this README.md detailing the steps taken.
Include a Public IP Address:144.126.197.25

The public IP address for the application is http://144.126.197.25.
Add a Screenshot: ![Screen Shot 2025-06-14 at 19 37 15](https://github.com/user-attachments/assets/3c8fc499-86cf-4a98-9dbf-2040d887a28d)



This README outlines the steps taken to create a dynamic web application prototype hosted on DigitalOcean.
The application showcases technical skills and project details, providing a solid foundation for future development and presentations.












