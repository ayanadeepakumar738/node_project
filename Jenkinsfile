pipeline {
    agent any

    stages {

        stage('Check Node.js') {
            steps {
                bat '''
                    set "PATH=C:\\Program Files\\nodejs;%PATH%"
                    node --version
                    npm --version
                '''
            }
        }

        stage('Backend Install') {
            steps {
                bat '''
                    set "PATH=C:\\Program Files\\nodejs;%PATH%"
                    cd backend
                    npm install
                '''
            }
        }

        stage('Backend Syntax Check') {
            steps {
                bat '''
                    set "PATH=C:\\Program Files\\nodejs;%PATH%"
                    cd backend
                    node --check index.js
                '''
            }
        }

        stage('Frontend Install') {
            steps {
                bat '''
                    set "PATH=C:\\Program Files\\nodejs;%PATH%"
                    cd frontend
                    npm install
                '''
            }
        }

        stage('Frontend Build') {
            steps {
                bat '''
                    set "PATH=C:\\Program Files\\nodejs;%PATH%"
                    cd frontend
                    npm run build
                '''
            }
        }
    }

    post {
        success {
            echo 'Node.js project build completed successfully!'
        }

        failure {
            echo 'Build failed. Check the Jenkins console output.'
        }
    }
}
