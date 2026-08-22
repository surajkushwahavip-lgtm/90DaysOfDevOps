# Day 08 – Cloud Server Setup: Docker, Nginx & Web Deployment

Today I practiced setting up and managing a cloud server using an Ubuntu EC2 instance.

The main focus was installing Docker and Nginx, checking their services, and working with Nginx logs.

## Task

- Connect to an Ubuntu cloud server using SSH
- Update and upgrade the system
- Install Docker
- Verify Docker is running
- Run the Docker hello-world container
- Install Nginx
- Verify the Nginx service
- Check Nginx log files
- Save Nginx logs into a separate file

## 1. Update the System

First, I updated the package list and upgraded the available packages.


sudo apt update
sudo apt upgrade -y


## 2. Install Docker

I installed Docker from the Ubuntu package repository.


sudo apt install docker.io -y


After installation, I checked the Docker version:


docker --version


Output from my server:


Docker version 29.1.3, build 29.1.3-0ubuntu4.1


I also checked the Docker service:


sudo systemctl status docker


Docker was running successfully:


Active: active (running)


## 3. Test Docker

To make sure Docker was working correctly, I ran the test container:


sudo docker run hello-world


Docker pulled the hello-world image and started the container successfully.

## 4. Install Nginx

Next, I installed Nginx:


sudo apt install nginx -y


Then I checked the service:


sudo systemctl status nginx


Nginx was running successfully:


Active: active (running)


## 5. Check Nginx Logs

I checked the Nginx log directory:


ls -l /var/log/nginx/


The main log files were:


access.log
error.log


I checked the latest entries using:


sudo tail -n 20 /var/log/nginx/access.log
sudo tail -n 20 /var/log/nginx/error.log


## 6. Save Nginx Logs

I practiced combining the Nginx access and error logs into a file:


sudo cat /var/log/nginx/access.log /var/log/nginx/error.log > nginx-logs.txt


I also practiced opening the file with:


vim nginx-logs.txt


## Challenge Faced

While checking the Nginx service, I accidentally typed:


sudosystemctl status nginx


This returned:


command not found


I corrected the command by adding the space:


sudo systemctl status nginx


After that, the Nginx service status showed:

Active: active (running)

I also got a No such file or directory message while checking nginx-logs.txt, so I practiced creating/opening the log file again.

## What I Learned

- How to update and upgrade an Ubuntu cloud server.
- How to install and verify Docker on a cloud VM.
- How to check whether Docker and Nginx services are running using systemctl.
- Where Nginx stores its access and error logs.
- How tail can be used to inspect recent log entries.
- Small command mistakes can cause errors, so checking the exact command syntax is important.

## Why This Matters for DevOps

This practice helped me understand some basic but important DevOps tasks:

- Cloud server management
- Linux package management
- Docker installation and verification
- Web server deployment
- Service monitoring
- Basic log management

This is another step toward understanding how applications and services are managed on real cloud servers.

## Screenshots

- 01-apt-update.png – System package update
- 02-apt-upgrade.png – Package upgrade
- 03-docker-install.png – Docker installation
- 04-docker-verify.png – Docker version and service verification
- 05-nginx-install.png – Nginx installation
- 06-nginx-status-and-logs.png – Nginx service and log checking

## Commands Practiced


sudo apt update

sudo apt upgrade -y

sudo apt install docker.io -y

docker --version

sudo systemctl status docker

sudo docker run hello-world

sudo apt install nginx -y

sudo systemctl status nginx

ls -l /var/log/nginx/

sudo tail -n 20 /var/log/nginx/access.log

sudo tail -n 20 /var/log/nginx/error.log

sudo cat /var/log/nginx/access.log /var/log/nginx/error.log > nginx-logs.txt

vim nginx-logs.txt


#90DaysOfDevOps #Day08 #DevOpsKaJosh #TrainWithShubham
