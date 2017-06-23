pipeline {
  agent any
  stages {
    stage('Setup Environment') {
      steps {
        sh '''echo "checking PATH:"+PATH;
echo "currelt working directory:"+pwd;
cd ./KubernetesMicroservices/
'''
      }
    }
    stage('Build') {
      steps {
        sh '/opt/gradle/gradle-3.4.1/bin/gradle clean build'
      }
    }
  }
}