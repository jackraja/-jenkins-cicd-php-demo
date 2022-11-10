pipeline {
  environment {
    registry = "jackraja/-jenkins-cicd-php-demo"
    dockerImage = ''
  }
  agent slave
  stages {
    stage('Cloning Git') {
      steps {
        git 'https://github.com/jackraja/-jenkins-cicd-php-demo.git'
      }
    }
    stage('Building image') {
      steps{
        script {
          dockerImage = docker.build registry + ":$BUILD_NUMBER"
        }
      }
    }
