pipeline {
    agent {
        docker {
            image 'node:16'  // Using Node.js 16 Docker image
            reuseNode true   // Reuse the same node for multiple stages
        }
    }

    stages {
        stage('Install Dependencies') {
            steps {
                // Run npm install to install dependencies
                sh 'npm install --save'
            }
        }

        stage('Build') {
            steps {
                // Add build commands if required
                echo 'Building the application...'
            }
        }

        stage('Test') {
            steps {
                // Add test commands if required
                echo 'Running tests...'
                sh 'npm test'
            }
        }

        stage('Deploy') {
            steps {
                // Add deployment steps if required
                echo 'Deploying the application...'
            }
        }
    }

    post {
        always {
            // Clean up Docker resources after pipeline execution
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
