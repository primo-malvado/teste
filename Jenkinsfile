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
    stage('publish') {
      steps {
        catchError() {
          sh 'npm publish'
          emailext(subject: 'eroor ', body: 'nao compilou', attachLog: true, from: 'rcosta@grupopie.com', to: 'rcosta@grupopie.com', replyTo: 'rcosta@grupopie.com')
        }

      }
    }
  }
}