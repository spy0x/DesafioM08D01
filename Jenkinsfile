pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out code..'
                git branch: 'main',
                    url: 'https://github.com/spy0x/DesafioM08D01.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the app..'
                sh 'npm install' // Ensure dependencies are installed
          }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the app..'
                script {
                    // Build the Docker image (assumes Dockerfile is in root)
                    docker.build('proyecto-desafiom08:latest')
                    // Alternative with more control:
                    // docker.build("your-image-name", "--file ./path/to/Dockerfile .")
                }
            }
        }
    }
}
