pipeline {
    agent any

    environment {
        PYTHON = '"C:\\Users\\Rabi Sankar Kar\\AppData\\Local\\Programs\\Python\\Python314\\python.exe"'
    }

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Create Docker Image') {
            steps {
                bat 'docker build -t etl-app .'
            }
        }

        
        stage('Run Docker Container') {
            steps {
                bat 'docker run -d -p 8501:8501 --name etl-container etl-app'
            }
        }

    }
    post {

        success {
            echo 'Docker deployment successfully.'
        }

        failure {
            echo 'Pipeline failed.'
        }

    }
}