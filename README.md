# Docker + Nginx Website CI/CD Pipeline on AWS

## Project Overview

Built and deployed a static website using Docker and Nginx on an AWS EC2 Ubuntu instance. Implemented a GitHub Actions CI pipeline to automate Docker image builds and validate the Nginx configuration whenever code is pushed to the `main` branch or a pull request is created.

## Technologies Used

- **AWS EC2** – Cloud server for hosting the website
- **Docker** – Containerization of the website
- **Nginx** – Web server for serving static content
- **Git & GitHub** – Version control and source code management
- **GitHub Actions** – Automated CI workflow
- **HTML, CSS and JavaScript** – Website development
- **Linux (Ubuntu)** – Server administration

## Project Features

- Created a Docker image using a custom Dockerfile.
- Served static website files through an Nginx container.
- Configured Nginx using a custom server configuration.
- Automated Docker image builds using GitHub Actions.
- Validated Nginx configuration during the CI workflow.
- Deployed the containerized website on an AWS EC2 Ubuntu instance.
- Configured port mapping to make the website accessible through the EC2 public IP.
- Used Docker commands to manage and troubleshoot the container.

## Project Structure

```text
docker-nginx-cicd-pipeline/
├── .github/
│   └── workflows/
│       └── ci.yml
├── nginx/
│   └── default.conf
├── index.html
├── style.css
├── script.js
├── Dockerfile
├── compose.yaml
└── README.md
```

## Run Locally

### Build the Docker image

```bash
docker build -t devops-website:latest .
```

### Run the container

```bash
docker run -d --name devops-website -p 8080:80 devops-website:latest
```

### Access the website

Open `http://localhost:8080` in your browser.

### Validate Nginx configuration

```bash
docker run --rm devops-website:latest nginx -t
```

## GitHub Actions CI Pipeline

The workflow performs the following steps:

1. Checks out the source code.
2. Builds the Docker image.
3. Tests the Nginx configuration.

The pipeline runs on pushes and pull requests targeting the `main` branch.

## AWS EC2 Deployment

- Used an Ubuntu EC2 instance as the deployment server.
- Built and ran the Docker container on the EC2 instance.
- Mapped the container's port 80 to the server's port 80.
- Configured the EC2 security group to allow HTTP traffic.
- Accessed the website through the EC2 public IPv4 address.

## Key Learnings

- Docker image creation and container management.
- Nginx configuration and static website hosting.
- GitHub Actions workflow creation using YAML.
- Linux server administration and troubleshooting.
- AWS EC2 deployment and security group configuration.
- CI pipeline automation and basic cloud deployment.

## Author

Vishal Choubey

GitHub: https://github.com/choubeyvishal125-hub
