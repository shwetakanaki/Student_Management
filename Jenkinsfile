pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/ursmaheshj/Student_Management.git', branch: 'main'
            }
        }

        stage('Build & Deploy') {
            steps {
                // Navigate to project directory

                // Ensure Docker Compose is installed
             //   sh 'sudo docker ps -a'

                // Build and start containers
                sh '''
                    sudo docker build -t python:t1 .
                    sudo  docker run -d -p 8001:8001 python:t1

                  # sudo docker compose -f docker_compose.yml build
                    
                '''
            }
        }
    }

    post {
        success {
            echo 'Deployment finished successfully!'
        }
        failure {
            echo 'Deployment failed!'
        }
    }
}
