pipeline {
    agent any
    stages {
    stage('Clone repository') {
        steps {
             
        git credentialsId: 'github-credentials', url: 'https://github.com/jackraja/-jenkins-cicd-php-demo.git'
    }
    
    }    
}
}
