# CI/CD Pipeline Setup for Java Project

## Overview
This repository contains instructions and configurations to set up a CI/CD pipeline using Jenkins, SonarQube, Nexus, and Tomcat for a Java web application.

### Architecture
The CI/CD pipeline includes the following components:
- **Git Repository**: Source code repository for the Java project.
- **Jenkins**: Automation server for building, testing, and deploying applications.
- **SonarQube**: Code quality and security analysis tool.
- **Nexus**: Artifact repository manager for storing build artifacts.
- **Tomcat**: Web server and servlet container to deploy the Java application.

## Steps to Setup

### Step 1: Get the Java project from Git repository
Clone the Java project from the Git repository:

```bash
git clone https://github.com/shivxm03/Jenkins-HandsOn-git-maven-sonarqube-nexus-tomcat-CI-CD.git
```
### Step 2: Create AWS EC2 instance for Jenkins, SonarQube, Nexus and Tomcat (Instance type: t2.medium)

![Screenshot 2024-06-14 204202](https://github.com/shivxm03/Jenkins-HandsOn-git-maven-sonarqube-nexus-tomcat-CI-CD/assets/157244434/84e58550-a1a5-4642-8780-8fea3879f45f)

### Step 3: Install Jenkins on Linux server (e.g., AWS EC2 t2.medium)
 
 [Jenkins installation guide](https://www.jenkins.io/doc/book/installing/linux/ )

 [Maven installation guide](https://maven.apache.org/install.html))

 ### Step 4: Install SonarQube on Linux server
 
 [SonarQube installation guide](https://www.sonarsource.com/products/sonarqube/downloads/)

 ### Step 5: Install Nexus on Linux server
 
 [Nexus installation guide](https://help.sonatype.com/en/download.html)

 ### Step 6: Install and Configure Tomcat on Linux server
 
 [Tomcat installation guide](https://tomcat.apache.org/download-90.cgi)

 ### Step 7: Configure SonarQube, Maven in Jenkins

Add credentials for SonarQube, Nexus, and Tomcat in Jenkins global credentials.

![Screenshot 2024-06-14 211216](https://github.com/shivxm03/Jenkins-HandsOn-git-maven-sonarqube-nexus-tomcat-CI-CD/assets/157244434/638c51fb-bd74-40f7-83a4-259df9696696)

### Step 8: Create Pipeline Job in Jenkins:

![Screenshot 2024-06-28 045501](https://github.com/shivxm03/Jenkins-HandsOn-git-maven-sonarqube-nexus-tomcat-CI-CD/assets/157244434/209bebb9-3cf2-4b8c-84a9-256dbbf66976)

## A Pipeline script is written as different steps as follows:

Stage : Tool Install : Sets up tools required for the pipeline execution.
Stage : Git Checkout : Retrieves the source code from a Git repository.
Stage : Build Maven Application : Compiles and packages the Maven application
Stage : Generate SonarQube Analysis : Runs SonarQube analysis on the project.
Stage : Upload WAR file to nexus : Uploads the packaged artifact (WAR file) to a Nexus repository.
Stage : Deploy WAR file to Tomcat : Copies the War file from Nexus to a Tomcat server for deployment.

View Pipeline script  [Here](https://github.com/shivxm03/Jenkins-HandsOn-git-maven-sonarqube-nexus-tomcat-CI-CD/blob/main/jenkinsfile-cicd)

### Output of SonarQube Analysis:

![Screenshot 2024-06-14 214909](https://github.com/shivxm03/Jenkins-HandsOn-git-maven-sonarqube-nexus-tomcat-CI-CD/assets/157244434/708ffb18-502b-47a0-a3dc-3ccf13dc995a)

### Creating Repository in Nexus(Maven2 Hosted): testnexusrepo

![Screenshot 2024-06-14 213149](https://github.com/shivxm03/Jenkins-HandsOn-git-maven-sonarqube-nexus-tomcat-CI-CD/assets/157244434/5669095a-3b61-4cc1-b5a8-98e1b81932a5)

## WAR file in nexus:

![Screenshot 2024-06-14 213218](https://github.com/shivxm03/Jenkins-HandsOn-git-maven-sonarqube-nexus-tomcat-CI-CD/assets/157244434/0b22249f-101c-42d0-b910-e831a7127eee)

### Screenshots of Jenkins:

![Screenshot 2024-06-14 212213](https://github.com/shivxm03/Jenkins-HandsOn-git-maven-sonarqube-nexus-tomcat-CI-CD/assets/157244434/6bf4572f-912f-4e95-8a7a-b9169514c09a)

![Screenshot 2024-06-14 215543](https://github.com/shivxm03/Jenkins-HandsOn-git-maven-sonarqube-nexus-tomcat-CI-CD/assets/157244434/8cc8a026-6e11-40a1-94b1-08c6629fdf69)

![Screenshot 2024-06-14 215323](https://github.com/shivxm03/Jenkins-HandsOn-git-maven-sonarqube-nexus-tomcat-CI-CD/assets/157244434/3a877714-8ec8-492d-a0e1-ce54982a1eac)

![Screenshot 2024-06-14 220006](https://github.com/shivxm03/Jenkins-HandsOn-git-maven-sonarqube-nexus-tomcat-CI-CD/assets/157244434/0a2118cb-4565-417a-85e6-81b4a07b9845)

![Screenshot 2024-06-14 215828](https://github.com/shivxm03/Jenkins-HandsOn-git-maven-sonarqube-nexus-tomcat-CI-CD/assets/157244434/529cd679-6bad-4394-9aa4-7095214da485)

![Screenshot 2024-06-14 215917](https://github.com/shivxm03/Jenkins-HandsOn-git-maven-sonarqube-nexus-tomcat-CI-CD/assets/157244434/0fd3d509-465c-40d9-8006-a2a7bfd08e51)


