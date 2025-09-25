pipeline {
    agent any

    stages {
        stage('Build') {
            steps{
                echo('Building the application...')
                sh('./mvnw clean package')
            }
        }
        stage('Test') {
            steps {
                echo ('Running tests....')
                sh('./mvnw test')
            }
        }

        stage('Build Docker Image') {
            steps{
                echo('Building the docker image')
                sh('docker build -t mayhrem/todo-app/latest .')
            }
        }

        stage('Push todo-app to DockerHub') {
            steps{
                echo('Pushing the docker image to DockerHub...')
                sh('docker push mayhrem/todo-app:latest')
            }
        }
    }

}