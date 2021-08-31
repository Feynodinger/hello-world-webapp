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
          		withDockerRegistry(credentialsId: 'decker-cosmiccurve', toolName: 'docker') {
            		def image = docker.build("thecosmologicalcurvedecker/decker-server:$BUILD_NUMBER")
            		image.push()
          		}
        	}
      	}
        }
    }
}
