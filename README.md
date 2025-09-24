# TODO APP

Spring Boot: Java API -> TODO APP
Jenkins: Create a CICD pipeline
Docker: Create a jenkins container

1. Creating the jenkins container where our pipeline will be used
```bash
docker run -d -p 8080:8080 -p 50000:50000 --name jenkins-cicd jenkins/jenkins:lts
```