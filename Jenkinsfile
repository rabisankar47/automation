pipeline {
    agent any

    environment {
        PYTHON = 'C:\Users\Rabi Sankar Kar\AppData\Local\Programs\Python\Python314\python.exe'
    }

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Run ETL File') {
            steps {
                bat "${env.PYTHON} etl.py"
            }
        }

    }

    post {

        success {
            echo 'Pipeline executed successfully.'
        }

        failure {
            echo 'Pipeline failed.'
        }

    }
}