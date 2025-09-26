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
                script {
                    withCredentials([usernamePassword(credentials: 'dockerhub-creds', usernameVariable: 'DOCKERHUB_USERNAME', passwordCredentials: 'DOCKERHUB_PASSWORD')]){
                        sh('docker login -u ${DOCKERHUB_USERNAME} -p ${DOCKERHUB_PASSWORD}')
                        sh('docker push mayhrem/todo-app:latest')
                    }
                }
            }
        }
    }

}