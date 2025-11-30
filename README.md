# Automated Static Website Deployment Using Terraform, Jenkins & Nginx

## Project Overview

**This project demonstrates how to provision cloud infrastructure using Terraform, automate deployment using Jenkins CI/CD, and host a static website on an EC2 instance with Nginx.**
**The pipeline automatically deploys code when changes are pushed to GitHub using a webhook trigger.**


## Requirements

- Terraform – Infrastructure provisioning

- AWS EC2 – Cloud virtual machine

- NGINX – Web server

- Jenkins – Continuous Integration / Deployment

- GitHub Webhook – Auto-trigger pipeline

- Ubuntu Linux – Server OS (jenkins)

- SSH Keys – Secure EC2 login

- Git – Version control

## Architecture

A[Developer] --> B[GitHub Push]
    B --> C[Webhook]
    C --> D[Jenkins Pipeline]
    D --> E[EC2 Server]
    E --> F[NGINX]
    F --> G[Website Live]


## Project Structure

static-website-project/
│
├── HomePage.html
├── blog.html
├── contactus.html
├── Servicespage.htm
├── Projectpage.htm
├── *.css
├── jenkinsfile
├──  README.md
├──  Terraform files 
└──  Images

## Prerequisites

- AWS Account

- IAM User with EC2 permissions or Access key and secret key

- Terraform installed

- A key pair created in AWS

- GitHub repository with static website code

- VS Code

- Jenkins installed and configured

## Infrastructure Setup (Using Terraform)

 **1: Initialize Terraform**
        - 'terraform init'
        - 'terraform plan'
        - 'terraform apply'


**Terraform creates:**

- EC2 instance

- Security group

- Key pair

- User-data (Nginx installation)

**Web Server Setup (EC2) nginx installed autoatically using User-data script at /var/www/html**

- sudo apt update
- sudo apt install nginx git -y
- sudo systemctl start nginx
- sudo systemctl enable nginx


## Jenkins Pipeline Configuration

**Plugins Installed in Jenkins:**

- Git Plugin

- GitHub Plugin

- Pipeline Plugin

- SSH Agent Plugin

- Github integrator Plugin

**Credentials Setup**

- SSH key stored in:
     '/var/lib/jenkins/.ssh/FC-key.pem'


## Webhook Configuration

- GitHub Webhook URL: http://13.56.156.208:8080/github-webhook/

- Content Type: application/json

## NGINX Configuration

**To test different pages as default we updated:**

'/etc/nginx/sites-available/default'

'index HomePage.html blog.html Projectpage.htm Servicespage.htm contactus.html index.html;'

## Access Website

'http://13.56.156.208'


## Conclusion

**This project automates the deployment of a static website using Terraform, Jenkins, and Nginx with GitHub Webhooks, enabling fast and reliable CI/CD. It demonstrates real-world DevOps practices including automation, cloud deployment, and server configuration.**


## Author:
- Pramod Mali

  - Github: https://github.com/Pramod581

  - Email: pramodnmali951@gmail.com

  -Linkedin: https://www.linkedin.com/in/pramod-mali-0a5650273










