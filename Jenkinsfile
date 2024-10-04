pipeline {
    agent {
        docker {
            image 'node:16'
            args '-u root' // Optional: use root user to avoid permission issues
        }
    }

    stages {
        stage('Install Dependencies') {
            steps {
                script {
                    // Ensure npm is installed
                    sh 'node -v'
                    sh 'npm -v'
                    
                    // Install dependencies using npm install --save
                    sh 'npm install --save'
                }
            }
        }

        // You can add more stages here, like 'Test' or 'Build'
    }
}
