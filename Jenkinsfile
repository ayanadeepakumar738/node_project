pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Backend Install') {
            steps {
                bat '''
                    cd backend
                    npm install
                '''
            }
        }

        stage('Frontend Install') {
            steps {
                bat '''
                    cd frontend
                    npm install
                '''
            }
        }

        stage('Backend Test') {
            steps {
                bat '''
                    cd backend
                    npm test
                '''
            }
        }

        stage('Frontend Build') {
            steps {
                bat '''
                    cd frontend
                    npm run build
                '''
            }
        }
    }

    post {
        success {
            echo 'Build and tests completed successfully!'
        }

        failure {
            echo 'Build failed. Check the Jenkins console output.'
        }
    }
}