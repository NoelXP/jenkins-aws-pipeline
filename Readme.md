# Jenkins Pipeline for AWS Infrastructure Deployment and Application Deployment

This repository contains a Jenkins Pipeline script to automate the deployment of AWS infrastructure using Terraform and Ansible, as well as the deployment of an application onto that infrastructure. The pipeline includes steps for polling a Git branch, rebuilding the AWS infrastructure, compiling and packaging an application, performing static code analysis, and deploying the application on the AWS infrastructure.

## Prerequisites

Before running the Jenkins Pipeline, ensure you have the following prerequisites set up:

1. **Jenkins**: Set up Jenkins on your server or Jenkins instance. Ensure you have necessary plugins installed (e.g., Git plugin, Pipeline plugin).
2. **AWS Account**: Create an AWS account and configure AWS CLI credentials with appropriate permissions.
3. **Terraform**: Install Terraform on the Jenkins server.
4. **Ansible**: Install Ansible on the Jenkins server.
5. **Git Repository**: Have a Git repository containing your application code.

## Pipeline Overview

The Jenkins Pipeline consists of the following stages:

1. **SCM Checkout**:
   - Poll the Git repository for changes and checkout the latest code.

2. **Infrastructure Deployment**:
   - Use Terraform to rebuild the AWS infrastructure based on the Terraform configuration files.
   - Use Ansible to provision any necessary configurations or dependencies on the infrastructure.

3. **Build**:
   - Compile the application code.
   - Package the application into a deployable artifact (e.g., JAR, WAR, Docker image).

4. **Static Code Analysis**:
   - Perform static code analysis using tools like SonarQube or ESLint to ensure code quality and identify any issues.

5. **Deployment**:
   - Deploy the application onto the AWS infrastructure.
   - Perform any necessary configuration updates or environment setup.

## Running the Pipeline

To run the Jenkins Pipeline, follow these steps:

1. **Configure Jenkins**:
   - Set up a Jenkins job or pipeline.
   - Point the pipeline to the Jenkinsfile in this repository.

2. **Configure Credentials**:
   - Add credentials in Jenkins for AWS CLI access and any other necessary credentials (e.g., Git credentials).

3. **Configure Pipeline Parameters**:
   - Modify the Jenkinsfile or use Jenkins Pipeline parameters to customize the pipeline behavior (e.g., AWS region, application version).

4. **Run Pipeline**:
   - Trigger the pipeline manually or set up triggers for automatic execution (e.g., polling SCM, webhooks).

5. **Monitor Execution**:
   - Monitor the pipeline execution in the Jenkins UI to ensure each stage completes successfully.