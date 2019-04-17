pipeline {
  agent any
  stages {
    stage('npm install') {
      steps {
        sh '''git pull && npm install
'''
      }
    }
    stage('build') {
      steps {
        sh '''npm run build
'''
      }
    }
  }
}