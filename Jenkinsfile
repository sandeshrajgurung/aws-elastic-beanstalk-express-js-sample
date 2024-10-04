pipeline {
    agent {
        docker {
            image 'node:16'  // Use Node.js version 16 Docker image
            reuseNode true   // Reuse the workspace for efficiency
        }
    }

    stages {
        stage('Install Dependencies') {
            steps {
                // Install project dependencies using npm
                sh 'npm install --save'
            }
        }

        stage('Build') {
            steps {
                // Add your build commands if required (optional)
                echo 'Building the application...'
            }
        }

        stage('Test') {
            steps {
                // Add your test commands if required (optional)
                echo 'Running tests...'
                sh 'npm test'  // Make sure you have a test script in package.json
            }
        }

        stage('Deploy') {
            steps {
                // Add your deployment commands (optional)
                echo 'Deploying the application...'
            }
        }
    }

    post {
        always {
            // Clean up Docker resources after the pipeline is completed
            sh 'docker system prune -f'
        }
        success {
            echo 'Pipeline executed successfully!'
        }
        failure {
            echo 'Pipeline failed. Please check the logs for details.'
        }
    }
}
