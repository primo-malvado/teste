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
        try{
          sh 'npm publish'
        }catch(err){
          currentBuild.result = 'FAILURE'
          emailext(subject: 'error ', body: 'nao compilou', attachLog: true, from: 'rcosta@grupopie.com', to: 'rcosta@grupopie.com', replyTo: 'rcosta@grupopie.com')
        }

      }
    }
  }
}