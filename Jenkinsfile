pipeline {
    agent { dockerfile true }
    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out code..'
                git 'https://github.com/spy0x/DesafioM08D01.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the app..'
                sh 'npm install' // Ensure dependencies are installed
                echo 'Running the app..'
                sh 'npm start'
          }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the app..'
                docker.build('my-docker-image:latest')
            }
        }
    }
}
