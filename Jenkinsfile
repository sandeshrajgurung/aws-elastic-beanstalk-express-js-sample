pipeline {
  agent {
    docker { 
      image 'node:16-alpine' 
      reuseNode true
    }
  }
  stages {
    stage('Test') {
      steps {
        sh 'node --version'
      }
    }
  }
}
