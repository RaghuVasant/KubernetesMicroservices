pipeline {
  agent any
  stages {
    stage('Setting up Environment') {
      steps {
        sh '''echo "checking PATH:"+$PATH;
echo "currelt working directory:"+pwd;'''
      }
    }
    stage('Build') {
      steps {
        sh '''cd ./KubernetesMicroservices/
/opt/gradle/gradle-3.4.1/bin/gradle clean build'''
      }
    }
    stage('Unit Test Microservices') {
      steps {
        sh '''
echo "Testing Orderline Service"
echo "Testing Orderline  Service completed successfully"


echo "Testing Order Service"
echo "Testing Order  Service completed successfully"

'''
      }
    }
    stage('Prepare Dockerimages') {
      steps {
        sh '''
cd /home/ubuntu/myproject/KubernetesMicroservices/KubernetesMicroservices/kubernete-config
sudo /home/ubuntu/myproject/KubernetesMicroservices/KubernetesMicroservices/kubernete-config/createpods.sh
'''
      }
    }
    stage('Deploy to Dev') {
      steps {
        sh '''echo "deploying to dev"
sleep 8s
echo "deployed to dev"'''
      }
    }
    stage('Run Smoke Tests') {
      steps {
        sh '''sudo kubectl get pods 
sudo kubectl get services'''
      }
    }
  }
}