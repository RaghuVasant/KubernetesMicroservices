pipeline {
  agent any
  stages {
    stage('Setup Environment') {
      steps {
        sh '''echo "checking PATH:"+PATH;
echo "currelt working directory:"+pwd;

'''
      }
    }
    stage('Build') {
      steps {
        sh '''cd ./KubernetesMicroservices/
gradle clean build'''
      }
    }
  }
}