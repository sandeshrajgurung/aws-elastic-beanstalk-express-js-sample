pipeline {
    agent {
        // Use the official Node 16 Docker image as the agent for this pipeline
        docker {
            image 'node:16'
        }
    }

    stages {
        stage('Install Dependencies') {
            steps {
                // Install dependencies using npm
                sh 'npm install --save'
            }
        }

        stage('Build') {
            steps {
                // Optionally include build steps if needed
                echo 'Building the application...'
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
                // Deploy step placeholder (to be customized based on deployment method)
                echo 'Deploying the application...'
            }
        }
    }

    post {
        always {
            // Cleanup Docker containers after the pipeline is done
            sh 'docker system prune -f'
        }
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed. Check the logs for errors.'
        }
    }
}
