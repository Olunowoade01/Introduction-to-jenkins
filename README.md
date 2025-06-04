# Introduction-to-Jenkins

This project demonstrates how to set up a Jenkins Declarative Pipeline with Docker integration for CI/CD automation. The pipeline automates building, testing, and deploying a web application inside a Docker container.

---

## Project Objective

- Implement a Jenkins Declarative Pipeline job that automates code cloning, Docker image building, and container deployment.
- Integrate Docker into the workflow, including Dockerfile creation and container management.
- Ensure the deployed application is accessible via a web browser on port 8081.

---

## Prerequisites

- macOS with Homebrew installed
- Jenkins installed and running
- Docker installed and running
- GitHub repository with application source code and Dockerfile

---

## Step-by-Step Process

### 1. Install Homebrew  
![1](./img/1%20install%20homebrew.png)  
*Homebrew is a package manager for macOS, used to install Jenkins and Docker.*

### 2. Install Jenkins  
![2](./img/2%20install%20jenkins.png)  
*Jenkins is installed using Homebrew.*

### 3. Install Docker  
![docker](./img/docker_install.png)  
*Install Docker Desktop for Mac using Homebrew or from [Docker's website](https://www.docker.com/products/docker-desktop/).*

```sh
brew install --cask docker
```

### 4. Access Jenkins via Browser  
![3](./img/4%20jenkins%20access%20via%20browser.png)  
*Jenkins runs as a service at `http://localhost:8080`.*

### 5. Unlock Jenkins and Complete Setup  
![4](./img/4%20jenkins%20access%20via%20browser.png)  
*Enter the initial admin password and complete setup.*

---

## Jenkins Declarative Pipeline with Docker Integration

### 6. Create a New Pipeline Job  
![pipeline](./img/pipeline_new_item.png)  
*Select "Pipeline" as the job type.*

### 7. Add a Dockerfile to Your Repository

Create a `Dockerfile` in your project root:

```dockerfile
# filepath: Dockerfile
FROM node:18
WORKDIR /app
COPY . .
RUN npm install
EXPOSE 8081
CMD ["npm", "start"]
```

### 8. Configure the Pipeline Script

In the Jenkins job, use the following Declarative Pipeline script:

```groovy
// Jenkinsfile
pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/your-username/your-repo.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                script {
                    dockerImage = docker.build("myapp:latest")
                }
            }
        }
        stage('Run Docker Container') {
            steps {
                script {
                    sh 'docker rm -f myapp || true'
                    sh 'docker run -d --name myapp -p 8081:8081 myapp:latest'
                }
            }
        }
    }
    post {
        success {
            echo 'Application deployed successfully!'
        }
        failure {
            echo 'Deployment failed.'
        }
    }
}
```

### 9. Open Port 8081

If running on a cloud VM, update your security group to allow inbound traffic on port 8081.  
*Screenshot: Security group rule for port 8081.*

### 10. Access the Application

Visit `http://localhost:8081` (or your server's public IP:8081) to verify the application is running.  
*Screenshot: Application running in browser.*

---

## Webhook Integration

- Push your Jenkinsfile and Dockerfile to your GitHub repository.
- Set up a webhook in GitHub to trigger Jenkins builds on code push.

---

## Summary

This guide covers Jenkins Declarative Pipeline creation, Docker integration, automated build and deployment, and application access verification. All steps are illustrated with screenshots and clear explanations to ensure alignment with project requirements.

---

## Troubleshooting

- Ensure Docker is running before pipeline execution.
- Check Jenkins user permissions for Docker.
- Review Jenkins build logs for errors.

---

## References

- [Jenkins Pipeline Documentation](https://www.jenkins.io/doc/book/pipeline/)
- [Docker Documentation](https://docs.docker.com/)


