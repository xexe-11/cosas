pipeline {
  agent any 

  stages {
    stage('Install') {
      steps { sh '/usr/bin/npm install' }
    }

    stage('Build') {
      steps { sh '/usr/bin/npm run-script build' }
    }
  }
}