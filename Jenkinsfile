pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                script {
                    dockerImage = docker.build("endpoint-app")
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                script {
                    sh 'docker rm -f endpoint-container || true'
                    dockerImage.run("-d -p 3000:3000 --name endpoint-container")
                }
            }
        }
    }
}
