# Flask CI/CD Pipeline Project 🚀

This project demonstrates a complete CI/CD pipeline for a Flask application using:

- GitHub
- AWS CodeBuild
- AWS Secrets Manager
- Amazon EC2
- SSH-based deployment automation

---

# Project Architecture

```text
Local PC
   ↓
Git Push
   ↓
GitHub Repository
   ↓
AWS CodeBuild
   ↓
AWS Secrets Manager
   ↓
SSH Deployment
   ↓
Amazon EC2 Flask Server

Technologies Used
Tool / Service	Purpose
Flask	Python web framework
GitHub	Source code repository
AWS CodeBuild	CI/CD automation
AWS Secrets Manager	Secure SSH key storage
Amazon EC2	Application hosting
SSH	Remote deployment
Project Structure
flask-ci-cd-project/
│
├── app.py
├── requirements.txt
├── buildspec.yml
├── README.md
└── templates/
Flask Application

The Flask app runs on:

http://<EC2-PUBLIC-IP>:5000

Example:

http://16.112.18.209:5000
CI/CD Workflow
1. Developer Pushes Code
git add .
git commit -m "Updated application"
git push
2. AWS CodeBuild Starts Build

CodeBuild:

Pulls source code from GitHub
Installs dependencies
Validates Flask application
Retrieves SSH key from Secrets Manager
3. Deployment to EC2

CodeBuild:

SSH connects to EC2
Pulls latest code
Restarts Flask application
Buildspec Configuration

The project uses buildspec.yml for:

Dependency installation
SSH setup
Flask validation
Automated deployment
Security Features
SSH private key stored securely in AWS Secrets Manager
IAM permissions used for controlled access
EC2 Security Group configured for:
Port 22 (SSH)
Port 5000 (Flask)
Running Flask Locally

Install dependencies:

pip install -r requirements.txt

Run application:

python app.py

Access:

http://127.0.0.1:5000
Future Improvements
Use Gunicorn instead of Flask development server
Add Nginx reverse proxy
Configure HTTPS using SSL
Add GitHub webhook automation
Implement Jenkins pipeline
Dockerize the application
Author

K Vikas

Learning Outcome

This project helped in understanding:

CI/CD concepts
AWS CodeBuild
EC2 deployment
Secrets Manager
SSH automation
DevOps troubleshooting
GitHub integration