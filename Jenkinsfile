pipeline {
  agent any
  stages {
    stage('Setting up Environment') {
      steps {
        sh 'echo "checking PATH:"$PATH'
      }
    }
    stage('Build') {
      steps {
        sh ''' cd ../kubernetes
gradle clean build'''
      }
    }
  }
}