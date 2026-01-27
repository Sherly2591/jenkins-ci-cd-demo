pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/Sherly2591/jenkins-ci-cd-demo.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t jenkins-demo:latest .'
            }
        }

        stage('Run Container') {
            steps {
                sh '''
                docker rm -f demo || true
                docker run -d --name demo -p 80:80 jenkins-demo:latest
                '''
            }
        }
    }
}
