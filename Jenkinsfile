pipeline {
    agent {
        docker {
            image 'node:16'
            reuseNode true
        }
    }

    stages {
        stage('Build') {
            steps {
                // Install dependencies using npm
                sh 'npm install --save'
            }
        }

        stage('Test') {
            steps {
                // Run tests (if any)
                echo 'Running tests...'
                sh 'npm test'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
            }
        }
    }

    post {
        always {
            // Clean up Docker resources after the build
            sh 'docker system prune -f'
        }
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed. Please check the logs.'
        }
    }
}
