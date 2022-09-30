pipeline {
  agent any
  stages {
    stage('checkout code') {
      steps {
        cleanWs()
        git(url: 'https://github.com/nananoam123/hello-world-war.git', branch: 'dev-ans', credentialsId: 'github')
      }
    }

    stage('build maven') {
      steps {
        sh '''mvn compile
mvn test
mvn package'''
      }
    }

    stage('clone repo') {
      steps {
        sh '''git clone https://github.com/nananoam123/N-E-A-infra.git
cd N-E-A-infra'''
        sh 'git config --global --add safe.directory /opt/tomcat/.jenkins/workspace/hello-world-war_master/N-E-A-infra'
        sh 'git checkout dev'
        sh '''cp Dockerfile /opt/tomcat/.jenkins/workspace/hello-world-war_master/.
'''
      }
    }

  }
}