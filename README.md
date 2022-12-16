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

# Step 1: Creation of Security Groups for Jenkins, Nexus, SonarQube
### a) Create an Amazon Linux 2 VM instance and call it "Jenkinsserver"
#### - Instance type: t2.large
#### - Security Group (Open): 8080, 9100 and 22 to 0.0.0.0/0
#### - Key pair: Select or create a new keypair
#### - Attach Jenkins server with IAM role having "AdministratorAccess"
#### - User data (Copy the following user data): 
#### - Launch Instance
#### - After launching this Jenkins server, attach a tag as Key=Application, value=jenkins

### b) Create an Create an Ubuntu 20.04 VM instance and call it "SonarQube"
#### - Instance type: t2.medium
#### - Security Group (Open): 9000, 9100 and 22 to 0.0.0.0/0
#### - Key pair: Select or create a new keypair
#### - User data (Copy the following user data):
#### - Launch EC2 Inatance 
