# Deep-Dive-Jenkins-Continuous-Integration

# Background
### In this project I integrate Jenkins, Maven, SonarQube, Nexus, and Slack in the Continuous Integration phase of a Jenkins CI/CD Pipeline.
### Continuous integration is a software development practice where members of a team use a version control system and frequently integrate their work to the same location, such as a main branch. Each change is built and verified to detect integration errors as quickly as possible. Continuous integration is focused on automatically building and testing code, as compared to continuous delivery, which automates the entire software release process up to production.https://docs.aws.amazon.com/codepipeline/latest/userguide/concepts-continuous-delivery-integration.html

### Diagramatic representaion of the Jenkins Continuous Integration Project

![Jenkins-CI-flow](https://user-images.githubusercontent.com/96470430/208033771-6f47a3c8-9d3b-43e1-8604-b28b86dc7ead.PNG)

# Prerequsits:
### It is assume that the following are already set or that the ready reader has knowlegde of
#### 1) AWS Account and the ability to navigate AWS console
#### 2) Basic Linux and understanding of shell scripts
#### 3) Git and GitHub : fundamental knowlede of common git and github commands 
#### 4) Jenkins installation and configuration
#### 5) Nexus installation and configuration
#### 6) SonarQube installation and configuration
#### 7) Slack channel of subscription to one 
#### 8) Troubleshooting skills

# Step 1: Install Jenkins, Nexus, SonarQube

### a) Create an Amazon Linux 2 VM instance and call it "JenkinsServer"
#### - Instance type: t2.large
#### - Security Group (Open): 8080, 9100 and 22 to 0.0.0.0/0
#### - Key pair: Select or create a new keypair
#### - Attach Jenkins server with IAM role having "AdministratorAccess"
#### - User data (Copy the following user data): https://github.com/SheyNjila1/Deep-Dive-Jenkins-Continuous-Integration/blob/main/userdata/Jenkins.sh
#### - Launch Instance
#### - After launching this Jenkins server, attach a tag as Key=Application, value=jenkins

### b) Create an Create an Ubuntu 20.04 VM instance and call it "SonarQubeServer"
#### - Instance type: t2.medium
#### - Security Group (Open): 9000, 9100 and 22 to 0.0.0.0/0
#### - Key pair: Select or create a new keypair
#### - User data (Copy the following user data): https://github.com/SheyNjila1/Deep-Dive-Jenkins-Continuous-Integration/blob/main/userdata/nexus.sh
#### - Launch EC2 Inatance 

### c) Nexus
#### - Create an Amazon Linux 2 VM instance and call it "NexusServer"
#### - Instance type: t2.medium
#### - Security Group (Open): 8081, 9100 and 22 to 0.0.0.0/0
#### - Key pair: Select or create a new keypair
#### - User data (Copy the following user data): https://github.com/SheyNjila1/Deep-Dive-Jenkins-Continuous-Integration/blob/main/userdata/sonarqube.sh
#### - Launch Instance

# Step 2: Verification steps to confirm proper installation of Jenkins, Nexux and SonarQube: 
#### SSH into each server using MobarXterm, Putty, Powershell or Termius or connect directly. Verify if userdata is correctly ustilized 

#### Access the servers on the brower using the public IP and default port 

![UnluckJenkins](https://user-images.githubusercontent.com/96470430/208053410-6e59b045-a118-441d-b417-3802f241aa8a.PNG)

### Customize Jenkins Plugins ---> Install Suggested Pluggins
### Install Suggested Plugins 
![Install Pluggins](https://user-images.githubusercontent.com/96470430/208054360-58913fd1-fbd9-40b1-b6d7-64428ee34510.PNG)
![Install Plugins in progress](https://user-images.githubusercontent.com/96470430/208054432-eec2ef2c-c636-4e8d-b172-d8cea057edc0.PNG)

### Create Firt Admin
![Create first Jenkins Admin](https://user-images.githubusercontent.com/96470430/208054503-7d2604c3-54fd-48de-8296-6e6291d463cd.PNG)

### Instance Configuration
![Instance Cinfiuration](https://user-images.githubusercontent.com/96470430/208054841-fca2e0da-7c62-4d77-a825-b448c5f0cfbe.PNG)

Jenkins Dasboard
![JenkinsDashboard](https://user-images.githubusercontent.com/96470430/208055131-7aa3b878-7824-4653-8572-49624b245b2d.PNG)

### Install Jenkins Plugins.
#### Maven Integration
#### Github Integration
#### Nexus Artifact Uploader
#### SonarQube Scanner
#### Slack Notification
#### Build Timestamp

![Integrate Jenkins Plugins](https://user-images.githubusercontent.com/96470430/208057341-ab6211f1-8f7c-47d0-87d6-3bdcf326e51e.PNG)


# Step 3: Configuration and integration of Jenkins, Maven, Nexus, SonarQube:
### a) JenkinsServer
### b) NexusServer
### c) SonarQubeServer


## References:
#### 1. https://www.udemy.com/course/devopsprojects/
#### 2. https://www.youtube.com/@RahulWagh


