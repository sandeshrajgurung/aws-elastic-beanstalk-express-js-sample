pipeline {
    agent any
    environment {
        PATH = "/usr/bin/npm:${env.PATH}"
    }
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
    }
}
