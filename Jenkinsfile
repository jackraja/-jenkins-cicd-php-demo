pipeline {
    agent any
    stage('Clone repository') {
        git credentialsId: 'github-credentials', url: 'https://github.com/jackraja/-jenkins-cicd-php-demo.git'
    }
    stage('Build image') {
       dockerImage = docker.build("jackraja/-jenkins-cicd-php-demo:latest")
    }
    
 stage('Push image') {
        withDockerRegistry([ credentialsId: "docker-hub-credentials", url: 'https://registry.hub.docker.com' ]) {
        dockerImage.push()
        }
    }    
}
