pipeline {
    agent any
    
    tools {
        dockerTool 'docker'
    }

    stages {
        stage('Git Clone') {
            steps {
                git changelog: false, poll: false, url: 'https://github.com/ayushpadia/hello-world-webapp.git'
            }
        }
    }
}
