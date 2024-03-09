# Automated Deployment of Java Application on Amazon EKS using Jenkins Pipeline.

![jenkins2](https://github.com/Ranaahmedit/CI-CD/assets/127610751/dfe5a7cc-1d73-4828-93e1-e145d35e96df)


# Jenkins Pipeline for Java Application Deployment on Amazon EKS

## Introduction
Jenkins Pipeline as Code provides flexibility and reusability, making it an excellent choice for automating deployment processes. In this tutorial, we'll discuss automating the deployment of a sample Java application on the Amazon Elastic Kubernetes Service (EKS) using Jenkins as a pipeline tool. The deployment will be achieved through a CI/CD pipeline using Jenkins declarative pipeline scripts.

## Prerequisites

### Prerequisite Knowledge
- Git, GitHub, Maven
- Docker, Docker Hub
- Docker image build, push, pull
- Kubernetes platform – EKS (Amazon Elastic Kubernetes Service)

### Prerequisite Setup
1. Jenkins installed on a Linux machine and accessible from the browser.
2. Maven installed on the Jenkins machine with proper MAVEN_HOME configuration.
3. Docker installed on the same machine where Jenkins is installed.
4. EKS cluster set up (or any other Kubernetes platform like AKS, GKE, etc.).
5. Java project or Java-based application source code hosted on GitHub.
6. Docker Hub account for storing images.

### Tools/Technology Used
- Git, GitHub
- Jenkins
- Docker
- Amazon Elastic Kubernetes Service (EKS)

## Step-by-Step Guide

### Step 1 – Getting Visual Idea about the Pipeline
- Overview of the chosen pipeline strategy, considering factors like cost and efficiency.
- Docker installed on the same machine as Jenkins for cost considerations.
- Addressing memory outage issues by deleting Docker images after pushing to Docker Hub.

### Step 2 – Configure Jenkins with JAVA_HOME, MAVEN_HOME
- Set JAVA_HOME and MAVEN_HOME paths under "Global Tool Configuration" in Jenkins.
- Obtain JAVA_HOME and MAVEN_HOME paths using the following commands:
    ```
    echo $JAVA_HOME
    echo $MAVEN_HOME
    ```
- Navigate to Manage Jenkins -> Global Tool Configuration.

### Step 3 – Configure Repository Credentials with Jenkins
- Configure credentials for both source code (GitHub) and Docker image repository (Docker Hub).
- Add GitHub token for private source code repositories.
- Add Docker Hub username and password.

### Step 4 – Install Jenkins Plugin to Integrate Kubernetes with Jenkins
- Install Kubernetes Credentials Plugin and Kubernetes CLI Plugin.
- Restart Jenkins after installation.

### Step 5 – Integrate Kubernetes with Jenkins
- Access Kubernetes cluster using the CLI interface.
- Copy the content of the kubeconfig file from the .kube directory and create a text file on your local desktop.
- In Jenkins dashboard, go to Manage Jenkins -> Manage Credentials and add a new credential of type "secret file." Choose the file you created and assign an ID.

### Step 6 – Prepare Kubernetes Manifest Files (YAML File)
- Create a Kubernetes manifest file to define the deployment object.
- Store the file on the Jenkins server, noting its location for use in the pipeline script.

### Step 7 – Prepare Jenkins Pipeline Script
- Utilize Jenkins pipeline as code (declarative type).
- Include the Jenkins declarative pipeline script for deploying the Java application on EKS.


## Conclusion
By following these steps, you'll have successfully set up a Jenkins pipeline for automating the deployment of a Java application on Amazon EKS, integrating key technologies like Git, Docker, and Kubernetes.

