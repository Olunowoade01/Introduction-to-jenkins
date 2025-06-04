# Introduction-to-Jenkins (Freestyle Job Edition)

This project demonstrates how to set up a Jenkins **Freestyle Job** with GitHub integration for basic CI/CD automation. The process covers job creation, source control management, webhook configuration, and build verification.

---

## Project Objective

- Create a Jenkins Freestyle Job.
- Integrate Jenkins with a GitHub repository for source code management.
- Configure build triggers using GitHub webhooks.
- Verify builds both manually and automatically after repository changes.

---

## Prerequisites

- macOS with Homebrew installed
- Jenkins installed and running
- GitHub account and repository with application source code

---

## Step-by-Step Process

### 1. Install Homebrew  
![1](./img/1%20install%20homebrew.png)  
*Homebrew is a package manager for macOS.*

### 2. Install Jenkins  
![2](./img/2%20install%20jenkins.png)  
*Jenkins is installed using Homebrew.*

### 3. Access Jenkins via Browser  
![3](./img/jenkins_access.png)  
*Jenkins runs at `http://localhost:8080`.*

### 4. Create a Jenkins Freestyle Job  
![4](./img/freestyle_new_item.png)  
- Click **New Item** in Jenkins.
- Enter a job name and select **Freestyle project**.
- Click **OK**.

### 5. Configure Source Code Management  
![5](./img/freestyle_scm.png)  
- In the job configuration, select **Git** under Source Code Management.
- Enter your GitHub repository URL.

### 6. Set Up Build Triggers  
![6](./img/freestyle_build_trigger.png)  
- Under **Build Triggers**, check **GitHub hook trigger for GITScm polling**.

### 7. Add a Simple Build Step  
- Under **Build**, add an **Execute shell** step (e.g., `echo "Build successful!"`).

### 8. Save and Run a Manual Build  
![7](./img/freestyle_manual_build.png)  
- Click **Build Now** to run the job manually.
- Confirm the build status is **SUCCESS**.

### 9. Configure GitHub Webhook  
![8](./img/github_webhook.png)  
- In your GitHub repo, go to **Settings > Webhooks**.
- Add your Jenkins URL: `http://<jenkins-server>/github-webhook/`.
- Select **Just the push event**.

### 10. Verify Automated Build Trigger  
- Make a commit/push to your GitHub repo.
- Confirm Jenkins triggers a new build automatically.
- ![9](./img/freestyle_auto_build.png)

---

## Summary

This guide covers Jenkins Freestyle Job creation, GitHub integration, webhook setup, and build verification—fulfilling the instructor’s requirements.

---

## Troubleshooting

- Ensure Jenkins has network access to GitHub.
- Confirm webhook delivery status in GitHub.
- Check Jenkins build logs for errors.

---

## References

- [Jenkins Freestyle Project](https://www.jenkins.io/doc/book/pipeline/getting-started/#freestyle-projects)
- [GitHub Webhooks](https://docs.github.com/en/webhooks)


