# 🚀 Deploying Docker on AWS EC2

This repository provides a step-by-step guide on how to deploy a Docker container (specifically a Streamlit/Python app) onto an AWS EC2 instance.

---

## 📋 Prerequisites
* An **AWS Account**.
* An **EC2 Instance** (Ubuntu is recommended).
* Basic knowledge of the terminal.

---

## 🛠️ Step-by-Step Deployment Guide

### 1. Create and Connect to EC2
* Launch an **EC2 Instance** (T2.micro or higher).
* Ensure your **Security Group** allows inbound traffic on the port your app uses (e.g., `8000` or `8501`).
* Connect via SSH:
  ```bash
  ssh -i "your-key.pem" ubuntu@your-ec2-public-ip



  # Update package list
sudo apt-get update

# Install Docker
sudo apt-get install -y docker.io

# Start and enable Docker service
sudo systemctl start docker
sudo systemctl enable docker

# Add your user to the docker group (to run docker without 'sudo')
sudo usermod -aG docker $USER

# Exit the terminal to apply group changes
exit



# Pull the image from Docker Hub
docker pull shakhawathossen/laptop

# Run the container
# Note: Map the host port to the container port (Host:Container)
docker run -d -p 8501:8501 shakhawathossen/laptop


## 🛠️ Essential Docker Commands

| Command | Description |
| :--- | :--- |
| `docker ps` | View all currently **running** containers. |
| `docker ps -a` | View **all** containers (including stopped/exited ones). |
| `docker stop <ID>` | Safely **stop** a running container using its ID or Name. |
| `docker logs <ID>` | Fetch the **logs** of a container (useful for debugging). |
| `docker images` | List all Docker **images** currently downloaded on your system. |
| `docker rm <ID>` | **Remove** a stopped container from the list. |
| `docker rmi <Image_ID>`| **Delete** a specific docker image. |

