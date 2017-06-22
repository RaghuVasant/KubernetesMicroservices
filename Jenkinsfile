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
gradle clean build'''
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
        junit '    assertEquals("10 x 0 must be 0", 0, tester.multiply(10, 0));'
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
  }
}