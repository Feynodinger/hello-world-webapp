pipeline {
    agent any
    
    tools {
        dockerTool 'docker'
    }

    stages {
        stage('Git Clone') {
            steps {
                git changelog: false, poll: false, url: 'https://github.com/Feynodinger/hello-world-webapp.git'
            }
        }
            stage('Deploy') {
        steps {
		script {
          		withDockerRegistry(credentialsId: 'dockerhub-ayush-personal', toolName: 'docker') {
            		def image = docker.build("Feynodinger/echo-server:$BUILD_NUMBER")
            		image.push()
          		}
        	}
      	}
        }
    }
}
