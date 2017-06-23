pipeline {
  agent any
  stages {
    stage('Setup Environment') {
      steps {
        sh '''sh echo "checking PATH:"+PATH;
echo "currelt working directory:"+pwd;
cd ./KubernetesMicroservices/'''
      }
    }
    stage('Build') {
      steps {
        sh 'gradle clean build'
      }
    }
  }
}