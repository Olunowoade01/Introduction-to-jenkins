# Introduction-to-Jenkins (Freestyle Job Edition)

This project demonstrates how to set up a Jenkins **Freestyle Job** with GitHub integration for basic CI/CD automation. The guide covers job creation, source control management, webhook configuration, and build verification, with supporting screenshots for each critical step.

---

## Prerequisites

- macOS with Homebrew installed
- Jenkins installed and running
- GitHub account and repository

---

## Step-by-Step Guide

### 1. Install Homebrew  
![1](./img/1%20install%20homebrew.png)  
*Homebrew installation on macOS, required for Jenkins setup.*

### 2. Install Jenkins  
![2](./img/02%20my%20first%20job.png)  
*Jenkins installation using Homebrew.*

### 3. Access Jenkins Dashboard  
**[Insert screenshot: Jenkins dashboard after first login]**  
*The Jenkins dashboard, confirming successful installation and access.*

### 4. Create a Freestyle Job  
**[Insert screenshot: "my-first-job" creation screen and dashboard view]**  
*Creating a new Freestyle Job named "my-first-job" in Jenkins.*

### 5. Configure Job Settings  
![3](./img/03.%20adding%20git%20repo.png)  
*Configuring the Freestyle Job to use a GitHub repository under Source Code Management.*

### 6. Save and View the Job  
**[Insert screenshot: Job configuration saved and visible in Jenkins dashboard]**  
*The "my-first-job" is now listed and ready to build.*

### 7. Trigger a Manual Build  
![4](./img/04%20build%20now.png)  
*Manually triggering a build by clicking "Build Now" in Jenkins.*

### 8. Confirm Manual Build Success  
![6](./img/06%20status%20showing%20.png)  
*Jenkins console output showing a successful manual build execution.*

### 9. Set Up GitHub Integration  
**[Insert screenshot: Jenkins job with GitHub repository connected]**  
*Jenkins job successfully connected to the GitHub repository.*

### 10. Configure Webhook in GitHub  
![8](./img/github_webhook.png)  
*Setting up a webhook in the GitHub repository to notify Jenkins of changes.*

### 11. Test Automated Build Trigger  
![9](./img/freestyle_auto_build.png)  
*Jenkins automatically triggers a build after a commit is pushed to GitHub.*

---

## Summary

This guide provides a complete walkthrough for Jenkins Freestyle Job creation, GitHub integration, webhook setup, and both manual and automated build verification. All required steps are documented with supporting screenshots to fulfill the instructor’s requirements.

---

## Troubleshooting

- Ensure Jenkins and GitHub can communicate (check network/firewall settings).
- Verify webhook delivery status in GitHub.
- Review Jenkins build logs for errors if builds do not trigger as expected.

---

## References

- [Jenkins Freestyle Project Documentation](https://www.jenkins.io/doc/book/pipeline/getting-started/#freestyle-projects)
- [GitHub Webhooks Documentation](https://docs.github.com/en/webhooks)

---

#


