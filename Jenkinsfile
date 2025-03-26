pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/spy0x/DesafioM08D01.git'
            }
        }

        stage('Build') {
            steps {
                sh 'npm install' // Ensure dependencies are installed
                sh 'npm start'
          }
        }

        stage('Deploy') {
            steps {
                docker.build('my-docker-image:latest')
            }
        }
    }
}
