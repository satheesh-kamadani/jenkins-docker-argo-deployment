# End-to-End CI/CD Pipeline with Jenkins, SonarQube, Docker, ArgoCD & Kubernetes

This project demonstrates a complete CI/CD pipeline integrating Jenkins, SonarQube, Docker, ArgoCD, and Kubernetes for automating the build, test, and deployment lifecycle of a Spring Boot application

Architecture Diagram

![Screenshot 2023-03-28 at 9 38 09 PM](https://user-images.githubusercontent.com/43399466/228301952-abc02ca2-9942-4a67-8293-f76647b6f9d8.png)


Here are the step-by-step details to set up an end-to-end Jenkins pipeline for a Java application using SonarQube, Argo CD, Helm, and Kubernetes:

Prerequisites:

   -  Java application code hosted on a Git repository
   -  Jenkins server
   -  Kubernetes cluster(Minikube)
   -  Argo CD


Steps:

    1. Install the necessary Jenkins plugins:
       1.1 Git plugin
       1.2 Maven Integration plugin
       1.3 Docker Pipeline plugin
       1.4 Sonarqube scanner plugin

    2. Create a new Jenkins pipeline:
       2.1 In Jenkins, create a new pipeline job and configure it with the Git repository URL for the Java application.
       2.2 Add a Jenkinsfile to the Git repository to define the pipeline stages.

    3. Define the pipeline stages:
        Stage 1: Checkout the source code from Git.
        Stage 2: Build the Java application using Maven and run unit tests
        Stage 3: Run SonarQube analysis to check the code quality.
        Stage 4: Build a Docker image of the application and push it to DockerHub or any container registry.
        Stage 5: Use a shell script to update the Docker image tag in the deployment.yml

    4. Argo CD deployed application on to kubernetes cluster:
        4.1 Set up Minikube as your local Kubernetes cluster.
        4.2 Install Argo CD inside Minikube. 
        4.3 Configure Argo CD to watch the Git repository so that it automatically detects updated deployment manifest files and deploys the application to the Kubernetes cluster.

This end-to-end Jenkins pipeline will automate the entire CI/CD process for a Java application, from code checkout to production deployment, using popular tools like SonarQube, Argo CD and Kubernetes.
