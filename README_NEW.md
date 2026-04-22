# ACEest Fitness & Gym – DevOps CI/CD Pipeline Project

## 📌 Project Overview

ACEest Fitness & Gym is a Flask-based gym management web application developed as part of a DevOps assignment. The project demonstrates end-to-end DevOps practices including source control, automated testing, containerization, CI/CD pipelines, code quality analysis, and Kubernetes deployment.

---

## 🎯 Objectives

- Build and manage a Flask-based gym application
- Implement version control using Git & GitHub
- Automate testing using Pytest
- Containerize the application using Docker
- Implement CI/CD using GitHub Actions and Jenkins
- Perform static code analysis using SonarQube
- Deploy the application using Kubernetes
- Demonstrate rolling updates with zero downtime

---

## 🛠️ Tech Stack

| Category | Tool |
|---------|------|
| Backend | Python, Flask |
| Testing | Pytest |
| Version Control | Git, GitHub |
| CI/CD | GitHub Actions, Jenkins |
| Containerization | Docker |
| Code Quality | SonarQube |
| Orchestration | Kubernetes |
| Registry | Docker Hub |

---

## 📁 Project Structure

```text
aceest-fitness-app/
│── app.py
│── requirements.txt
│── Dockerfile
│── Jenkinsfile
│── sonar-project.properties
│── test_app.py
│── legacy_versions/
│── k8s/
│   ├── deployment.yaml
│   └── service.yaml
│── .github/workflows/main.yml

🚀 Local Setup
git clone https://github.com/Prabakaran93640/aceest-fitness-app.git
cd aceest-fitness-app
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
python app.py

Open browser:

http://127.0.0.1:5000

Default Login:

Username: admin
Password: admin

🧪 Manual Test Execution
pytest -v test_app.py

🐳 Docker Usage

Build image:

docker build -t aceest-app .

Run container:

docker run -p 5000:5000 aceest-app

📦 Docker Hub Images

Published images:

prabakaran2311/aceest-app:v1.0
prabakaran2311/aceest-app:v2.0
prabakaran2311/aceest-app:v3.0
prabakaran2311/aceest-app:v3.2.4
prabakaran2311/aceest-app:latest

🔁 CI/CD Pipeline
GitHub Actions

Triggered on every push / pull request.

Stages:

Checkout Code
Install Dependencies
Run Pytest
Build Docker Image
Jenkins

Used as secondary build validation pipeline.

Stages:

Source Checkout
Build Validation
Test Validation
SonarQube Integration Stage
Build Success Confirmation

🔍 SonarQube

Used for static code quality checks:

Bugs
Code Smells
Maintainability
Duplications
☸ Kubernetes Deployment

Deploy:

kubectl apply -f k8s/deployment.yaml
kubectl apply -f k8s/service.yaml

Check:

kubectl get pods
kubectl get svc

🔄 Rolling Update
kubectl set image deployment/aceest-app aceest-app=prabakaran2311/aceest-app:latest
kubectl rollout status deployment/aceest-app

🏁 Learning Outcomes
CI/CD pipeline implementation
Docker image versioning
Jenkins build automation
SonarQube code quality scanning
Kubernetes deployments and rolling updates
Real-world DevOps workflow understanding

👨‍💻 Author

Prabakaran Dharmaraj
M.Tech Software Engineering