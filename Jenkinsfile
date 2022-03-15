pipeline {
  agent {
    docker { image 'node:10.2-alpine' }
  } 

  stages {
    stage('Install') {
      steps { sh 'npm install' }
    }
    
    stage('Test') {
      parallel {
        stage('Static code analysis') {
            steps { sh 'npm run-script lint' }
        }
        stage('Unit tests') {
            steps { sh 'npm run-script test' }
        }
      }
    }
    
    stage('Build') {
      steps { sh 'npm run-script build' }
    }
  }
}
