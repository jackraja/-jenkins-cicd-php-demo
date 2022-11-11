pipeline{

	agent {label 'slave'}

	environment {
		DOCKERHUB_CREDENTIALS=credentials('docker-hub-credentials')
	}

	stages {
	    
	    stage('gitclone') {

			steps {
				git 'https://github.com/jackraja/-jenkins-cicd-php-demo.git'
			}
		}

		stage('Build') {

			steps {
				sh 'docker build -t jackraja/-jenkins-cicd-php-demo:latest .'
			}
		}

		stage('Login') {

			steps {
				sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
			}
		}

		stage('Push') {

			steps {
				sh 'docker push jackraja/-jenkins-cicd-php-demo:latest'
			}
		}
	}

	post {
		always {
			sh 'docker logout'
		}
	}

}
