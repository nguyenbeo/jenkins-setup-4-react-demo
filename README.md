# spring-react-2-factor-auth
A demo shows how to set up Jenkins Pipeline for React JS application

# Overview
Continuous Integration (CI) is one of the most famous terms within IT world
recently. It aims to prevent integration problems, referred to as
"integration hell" in early descriptions of XP. CI is not universally accepted
as an improvement over frequent integration, so it is important to distinguish
between the two as there is disagreement about the virtues of each.

In this demonstration, I will try to set up Jenkins or specifically Jenkins'
Blue Ocean to run a React project as a pipeline.

# Technology
* Docker
* Jenkins
* Node JS
* React JS

# Important notes
* Jenkinsfile is the pre-defined pipeline where Jenkins will based on to run.
* Dockerfile is the file used to create Docker Image.

# How to run
In order to run this, you need to install some prerequisites:
* Docker

## Run Jenkins Blue Ocean as Docker Container
* Run the following command: docker run --rm -u root -p 8080:8080 -v jenkins-data:/var/jenkins_home -v /var/run/docker.sock:/var/run/docker.sock -v "$HOME":/home jenkinsci/blueocean
* Go to http://localhost:8080 from a web browser and run the initial setup wizard. Don't forget to choose "Suggested plugins".
* Browse to http://localhost:8080/blue and create a Jenkins job to point to this repository as a Github.

## Result
You will see the result of the job as a pipeline
