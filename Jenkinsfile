pipeline {
  agent any
  stages {
    stage('step1') {
      steps {
        echo 'print message 1'
        sh 'echo "aaa"'
      }
    }
    stage('npm install') {
      steps {
        sh '''npm install
npm run build
'''
      }
    }
  }
}