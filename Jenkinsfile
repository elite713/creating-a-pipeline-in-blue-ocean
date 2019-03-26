pipeline {
  agent {
    docker {
      image 'node:6-alpine'
      args '-p 3000:3000 -u root'
    }

  }
  stages {
    stage('Build') {
      steps {
        sh '''sudo rm -rf ./*
'''
        sh 'npm install'
      }
    }
    stage('Test') {
      environment {
        CI = 'true'
      }
      steps {
        sh './jenkins/scripts/test.sh'
      }
    }
  }
}