slave {   
    stage('Clone repository') {
        git credentialsId: 'git', url: 'https://github.com/jackraja/-jenkins-cicd-php-demo.git'
    }
    
    stage('Build image') {
       dockerImage = docker.build("jackraja/-jenkins-cicd-php-demo:latest")
    }
    
 stage('Push image') {
        docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-credentials')
         {
        dockerImage.push()
        }
    }    
}
