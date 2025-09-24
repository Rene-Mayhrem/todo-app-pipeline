pipeline {
    agent any

    stages {
        stage('Build') {
            steps{
                echo('BUilding the application...')
                sh('./mvnw clean package')
            }
        }
        stage('Test') {
            steps {
                echo ('Running tests....')
                sh('./mvnw test')

            }
        }
    }

}