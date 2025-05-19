pipeline {
    agent any

    stages {
        stage('Create an image') {
            steps {
                sh 'docker build . -t travel'
            }
        }
        stage('Docker run') {
            steps {
                sh 'docker run -p 3002:3000 --name container2 -d travel'
            }
        }
    }
}
