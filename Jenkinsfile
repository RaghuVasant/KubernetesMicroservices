pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh '''cd ./KubernetesMicroservices/KubernetesMicroservices

gradle clean build distDocker'''
      }
    }
  }
}