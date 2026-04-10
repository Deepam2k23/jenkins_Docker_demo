pipeline {
	agent any


	enviroment{
	Docker_Image = 'hello-world-python:latest'
	}
	
	stages {
		stage('Checkout') {
			steps{
				git branch: 'main', url:
				'https://github.com/Deepam2k23/jenkins_Docker_demo.git'

			}
		}

	stage('Docker Build'){
		steps {
			script {
			if (fileExists('Dockerfile')) {
				sh "docker build -t ${env.DOCKER_IMAGE} ."
				}  else {
					error "Dockerfile not found in the workspace. Please create one of your Python application."
					}
				}
			}
		}
	stage('Docker Run (Optional)') {
		steps {			sh "docker run --rm ${env.DOCKER_IMAGE"}}			}
		}
	}

	post {
		success {echo 'Success'}
		failure {echo 'failure'}	
		}
}
