pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git 'https://github.com/Khanh2411/flask-docker-app.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    dockerImage = docker.build("flask-demo")
                }
            }
        }

        stage('Run Container') {
            steps {
                script {
                    sh 'docker rm -f flask-app || true'
                    sh 'docker run -d -p 5000:5000 --name flask-app flask-demo'
                }
            }
        }
    }
}
