pipeline {
  agent any
  stages {
    stage('checkout code') {
      steps {
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

    stage('Docker build') {
      steps {
        sh '''docker-compose build 
docker-compose up -d '''
      }
    }

  }
}