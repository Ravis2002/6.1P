pipeline {
    agent any
    environment {
        DIRECTORY_PATH         = '/C:/Users/ravis/OneDrive/Documents/GitHub/6.1P       
        TESTING_ENVIRONMENT    = 'testing'                     
        PRODUCTION_ENVIRONMENT = 'RAvis-Production'         
    }
    stages {
        stage('Build') {
            steps {
                echo "Fetch the source code from the directory path specified by the environment variable: ${env.DIRECTORY_PATH}"
                echo 'Compile the code and generate any necessary artefacts'
            }
        }
        stage('Test') {
            steps {
                echo 'Unit tests'
                echo 'Integration tests'
            }
        }
        stage('Code Quality Check') {
            steps {
                echo 'Check the quality of the code'
            }
        }
        stage('Deploy') {
            steps {
                echo "Deploy the application to a testing environment specified by the environment variable: ${env.TESTING_ENVIRONMENT}"
            }
        }
        stage('Approval') {
            steps {
                echo 'Waiting for manual approval...'
                sleep time: 10, unit: 'SECONDS'
                echo 'Approval granted.'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo "Deploy the application to the production environment: ${env.PRODUCTION_ENVIRONMENT}"
            }
        }
    }
    post {
        success { echo 'Pipeline completed successfully.' }
        failure { echo 'Pipeline failed. Please check the logs.' }
    }
}
