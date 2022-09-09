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
        sh '''docker compose build 
docker compose up -d '''
      }
    }

    stage('tag') {
      steps {
        sh '''docker tag wordpress:latest wordpress:$(docker images | grep wordpress | awk \'{print $3}\')

docker tag mysql:5.7 mysql:$(docker images | grep mysql | awk \'{print $3}\')'''
      }
    }

  }
}