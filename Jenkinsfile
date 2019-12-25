node{
  stage('SCM Checkout') {
    git 'https://github.com/monbostest/java-code1.git'
    }
  stage('compile code') {
    sh 'mvn package'
    }
  stage('docker buid'){
   sh 'docker build -t nippy/myapp.$BUILD_NUMBER .'
  }
  stage('push'){
   sh 'docker login -u nippy -p Redhat@123456'
   sh 'docker push nippy/myapp.$BUILD_NUMBER'
  }
  stage('Deploy an Application'){
   sh 'docker run -d  -p 8003:8080 nippy/myapp.$BUILD_NUMBER  '
  }
  stage('This is deployed '){
   sh 'echo " this is done'
  }
}
