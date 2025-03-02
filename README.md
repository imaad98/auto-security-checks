# Secure Flask Web Application

This project is a secure web application built using **Python Flask**, containerized with **Docker**, and integrated with security tools like **SonarQube**, **OWASP ZAP**, and **Trivy**. The application is deployed using a **CI/CD pipeline** powered by **GitHub Actions**.

---

## Features

- **Secure Web Application**: A simple Flask app with best practices for security.
- **CI/CD Pipeline**: Automated testing, security scanning, and deployment.
- **Security Tools**:
  - **SAST (Static Application Security Testing)**: SonarQube.
  - **DAST (Dynamic Application Security Testing)**: OWASP ZAP.
  - **Container Scanning**: Trivy.
- **Dockerized**: The app is containerized for easy deployment.

---

## Tools Used

- **Web Framework**: Python Flask.
- **CI/CD**: GitHub Actions.
- **Security Tools**:
  - SonarQube (SAST).
  - OWASP ZAP (DAST).
  - Trivy (Container Scanning).
- **Containerization**: Docker.
- **Version Control**: Git.

---

## Prerequisites

Before running the project, ensure you have the following installed:

- **Windows with WSL** (Windows Subsystem for Linux).
- **Docker Desktop** (with WSL 2 integration enabled).
- **Python 3.9** or higher.
- **Git**.

---

## Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/imaad98/auto-security-checks.git
cd secure-flask-app

### 2. Set Up the Flask App

### 1. Install dependencies:
```bash
pip install flask

### 2. Run the app:
```bash
python3 app.py

### 3. Open your browser and navigate to http://localhost:5000.

### 3. Set Up Docker

### 1. Build the Docker image:
```bash
docker build -t your-docker-username/auto-security-checks .

### 2. Run the Docker container:
```bash
docker run -p 5000:5000 your-docker-username/auto-security-checks

### 3. Open your browser and navigate to http://localhost:5000.

### 4. Set Up CI/CD Pipeline

1. Add the following secrets to your GitHub repository:
   - `SONAR_TOKEN`: Your SonarQube token.
   - `DOCKER_USERNAME`: Your Docker Hub username.
   - `DOCKER_PASSWORD`: Your Docker Hub password.

2. Push changes to the `main` branch to trigger the CI/CD pipeline.

## CI/CD Pipeline

The CI/CD pipeline includes the following steps:

1. **Code Checkout**: Pulls the latest code from the repository.
2. **SAST Scan**: Runs SonarQube for static code analysis.
3. **DAST Scan**: Runs OWASP ZAP for dynamic application security testing.
4. **Docker Build**: Builds the Docker image.
5. **Trivy Scan**: Scans the Docker image for vulnerabilities.
6. **Docker Push**: Pushes the Docker image to Docker Hub.

## Security Tools

### 1. SonarQube (SAST)

- Used for static code analysis to identify vulnerabilities and code smells.
- Configured in the `.github/workflows/ci-cd.yml` file.

### 2. OWASP ZAP (DAST)

- Used for dynamic application security testing to identify runtime vulnerabilities.
- Configured in the `.github/workflows/ci-cd.yml` file.

### 3. Trivy

- Used for scanning Docker images for vulnerabilities.
- Integrated into the CI/CD pipeline.

## Project Structure
secure-flask-app/
├── .github/
│   └── workflows/
│       └── ci-cd.yml          # GitHub Actions workflow
├── app.py                     # Flask application
├── Dockerfile                 # Docker configuration
├── requirements.txt           # Python dependencies
├── README.md                  # Project documentation
└── .gitignore                 # Files to ignore in Git




