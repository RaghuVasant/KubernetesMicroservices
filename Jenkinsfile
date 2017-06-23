pipeline {
  agent any
  stages {
    stage('Setup Environment') {
      steps {
        sh '''echo "checking PATH:"$PATH;
echo "current working directory:" $PWD;
'''
      }
    }
    stage('Build') {
      steps {
        sh '''cd ./KubernetesMicroservices/
echo "current working directory:" $PWD;
/opt/gradle/gradle-3.4.1/bin/gradle clean build'''
      }
    }
  }
}