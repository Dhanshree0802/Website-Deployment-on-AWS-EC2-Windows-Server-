# Website Deployment on AWS EC2 (Windows Server)

This repository contains the procedure and resources for deploying a website on an AWS EC2 instance running Windows Server. The deployment process utilizes Remote Desktop Protocol (RDP) for setup and management.

## Table of Contents
- [Introduction](#introduction)
- [Prerequisites](#prerequisites)
- [Step-by-Step Procedure](#step-by-step-procedure)
  - [Create an AWS EC2 Instance](#1-create-an-aws-ec2-instance)
  - [Connect to Your EC2 Instance Using RDP](#2-connect-to-your-ec2-instance-using-rdp)
  - [Set Up the Web Server (IIS)](#3-set-up-the-web-server-iis)
  - [Deploy Your Website](#4-deploy-your-website)
  - [Manage and Monitor Your EC2 Instance](#5-manage-and-monitor-your-ec2-instance)
- [License](#license)

## Introduction
This guide provides detailed steps to deploy a website on an Amazon EC2 instance running Windows Server. The process covers creating an EC2 instance, connecting via RDP, installing IIS (Internet Information Services), and managing the server.

## Prerequisites
Before you begin, ensure you have the following:
- An AWS account.
- A locally installed RDP client (e.g., Remote Desktop Connection on Windows) or you will get the download link while connecting.
- Website files ready for deployment.
- Basic understanding of AWS and Windows Server.

## Step-by-Step Procedure

### 1. Create an AWS EC2 Instance
1. **Log in to AWS Management Console** and navigate to the EC2 Dashboard.
2. **Launch a New EC2 Instance**:
   - Choose **Microsoft Windows Server** as the AMI.
   - Select an appropriate instance type (e.g., `t2.micro` for free tier).
   - Configure instance details, add storage, and set up a security group with RDP, HTTP, and HTTPS rules.
   - Launch the instance and download the key pair file.
   
### 2. Connect to Your EC2 Instance Using RDP
1. **Get the Administrator Password**:
   - Decrypt the password using your key pair.
2. **Connect via RDP**:
   - Use Remote Desktop Connection to log in using the instance's public IP address and administrator credentials.

### 3. Set Up the Web Server (IIS)
1. **Install IIS**:
   - Open Server Manager and add the Web Server (IIS) role.
   - Verify the installation by navigating to `http://localhost` on the EC2 instance.
   
### 4. Deploy Your Website
1. **Upload Your Website Files**:
   - Transfer files to `C:\inetpub\wwwroot` using RDP or an FTP client.
2. **Configure IIS**:
   - Use IIS Manager to ensure your website is correctly configured and running.

### 5. Manage and Monitor Your EC2 Instance
1. **Monitoring**:
   - Set up CloudWatch for performance monitoring and alarms.
2. **Security**:
   - Regularly update the server and review Security Group rules.
3. **Backup**:
   - Use EBS snapshots for regular backups.


