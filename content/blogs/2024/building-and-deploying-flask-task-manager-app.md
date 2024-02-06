---
title: "Building and Deploying Flask Task Manager App"
date: 2024-02-03T15:04:46+05:30
draft: false
---

## Part 1: Application Creations

### Step 1: Project Setup

```bash
# Create a folder for the app
mkdir flask-task-manager-app
cd flask-task-manager-app

# Create a virtual environment
py -3 -m venv .venv

# Activate the virtual environment
.venv\Scripts\activate  # For Windows
source .venv/bin/activate  # For macOS
```

### Step 2: Project Structure and Dependencies

```bash
# Create necessary files and folders
touch app.py requirements.txt
mkdir templates
cd templates
touch add_task.html dashboard.html edit_task.html login.html register.html view_users.html
```

**requirements.txt:**

```plaintext
blinker==1.7.0
click==8.1.7
colorama==0.4.6
Flask==3.0.1
Flask-Login==0.6.3
Flask-SQLAlchemy==3.1.1
greenlet==3.0.3
itsdangerous==2.1.2
Jinja2==3.1.3
MarkupSafe==2.1.5
SQLAlchemy==2.0.25
typing_extensions==4.9.0
Werkzeug==3.0.1
```

### Step 3: App Implementation (app.py)

```python
# [App.py code]
```

### Step 4: Installation and Execution

```bash
# Install dependencies
pip install -r requirements.txt

# Run the application
python app.py
```

## Part 2: Docker Containerization

### Step 1: Docker Image Creation

```bash
# Build Docker image
docker build -t flask-app:latest .

# Save Docker image
docker save flask-app:latest > flask-app.tar
```

### Step 2: Running Docker Container

```bash
# Run Docker container locally
docker run -d -p 8001:8001 --name flask-app-container flask-app:latest
```

### Step 3: Docker Hub Integration

```bash
# Tag Docker image
docker tag flask-app rahuldabgotra/flask-app

# Push Docker image to Docker Hub
docker push rahuldabgotra/flask-app
```

### Step 4: Pulling and Running Docker Image from Docker Hub

```bash
# Pull Docker image from Docker Hub
docker pull rahuldabgotra/flask-app:latest

# Run Docker container from pulled image
docker run -d -p 8001:8001 --name flask-app-container rahuldabgotra/flask-app:latest
```

## Part 3: Deployment on Ubuntu Server

### Step 1: Setting Up Ubuntu

```bash
# Install required packages
sudo apt-get update
sudo apt-get install -y \
   apt-transport-https \
   ca-certificates \
   curl \
   gnupg-agent \
   software-properties-common

# Add Docker GPG key and repository
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
echo "deb [signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

# Install Docker
sudo apt-get update
sudo apt-get install -y docker-ce docker-ce-cli containerd.io

# Start Docker and add user to docker group
sudo systemctl start docker
sudo usermod -aG docker $USER

# Verify Docker installation
docker --version
docker run hello-world
```

### Step 2: Pull and Run Docker Image on Ubuntu

```bash
# Pull Docker image from Docker Hub
docker pull rahuldabgotra/flask-app:latest

# Run Docker container on Ubuntu
docker run -d -p 8001:8001 --name flask-app-container rahuldabgotra/flask-app:latest
```

This comprehensive guide covers the creation of a Flask Task Manager app, Docker containerization, and deployment on an Ubuntu server. Follow the step-by-step instructions to build, containerize, and deploy your Flask application.
