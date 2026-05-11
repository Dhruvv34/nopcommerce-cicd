pipeline {

    agent any

    environment {
        APP_NAME = "nopcommerce-app"
    }

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'docker compose build'
            }
        }

        stage('Run Containers') {
            steps {
                sh 'docker compose down || true'
                sh 'docker compose up -d'
            }
        }

        stage('Verify Containers Running') {
            steps {
                echo 'CI/CD pipeline executed successfully...'
                sh 'docker ps'
            }
        }
    }
}