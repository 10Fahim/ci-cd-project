# 🚀 CI/CD Pipeline with Jenkins & GitHub

This project demonstrates a complete CI/CD pipeline built using Jenkins, GitHub, and Docker. The pipeline automates the process of building, testing, containerizing, and deploying an application with every code push.

---

## 🛠️ Tech Stack

- Git & GitHub
- Jenkins (Pipeline as Code)
- Docker
- AWS EC2 (Deployment Server)
- Shell Scripting
- Python (Flask App)

---

## 📌 Project Overview

The goal of this project is to eliminate manual deployment by implementing a fully automated CI/CD pipeline.

Whenever code is pushed to the GitHub repository:
1. Jenkins is triggered via webhook
2. Code is fetched from GitHub
3. Docker image is built
4. Image is pushed to DockerHub
5. Application is deployed automatically on EC2

---

## 🔄 CI/CD Workflow

```text
Developer → GitHub Push → Webhook → Jenkins Pipeline → Docker Build → Docker Push → Deploy on EC2
