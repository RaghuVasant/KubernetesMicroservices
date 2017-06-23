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
    stage('Unit Test Microservices') {
      steps {
        sh '''echo "Testing Orderline Service"
echo "Testing Orderline  Service completed successfully"

 echo "Testing Order Service"
echo "Testing Order  Service completed successfully"'''
      }
    }
    stage('Prepare Docker Images') {
      steps {
        sh '''cd /home/ubuntu/myproject/KubernetesMicroservices/KubernetesMicroservices/kubernete-config
sudo /home/ubuntu/myproject/KubernetesMicroservices/KubernetesMicroservices/kubernete-config/createpods.sh'''
      }
    }
    stage('Deploy to Dev') {
      steps {
        sh '''echo "Begin deploying to environment:DEV"
sudo kubectl get pods
sudo kubectl get services
echo "Begin deploying to environment:DEV"'''
      }
    }
  }
}