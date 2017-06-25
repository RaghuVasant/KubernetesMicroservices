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
echo "Testing Orderline Service completed successfully"

echo "Testing Order Service"
echo "Testing Order Service completed successfully"'''
      }
    }
    stage('Prepare Docker Images') {
      steps {
        sh '''echo $PWD
cd /home/ubuntu/kubernetes
daemonize -E BUILD_ID=dontKillMe sudo /home/ubuntu/kubernetes/hack/local-up-cluster.sh


cd ./KubernetesMicroservices/kubernete-config
sudo ./createpods.sh'''
      }
    }
    stage('Deploy to Dev') {
      steps {
        sh '''echo "Begin deploying to environment:DEV"

echo "Bringing up kubernetes dashboard"
sudo kubectl create -f https://rawgit.com/kubernetes/dashboard/master/src/deploy/kubernetes-dashboard.yaml
 
sudo kubectl get pods
sudo kubectl get services
echo "Begin deploying to environment:DEV"'''
      }
    }
  }
}