pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/ursmaheshj/Student_Management.git', branch: 'master'
            }
        }

        stage('Build & Deploy') {
            steps {
                // Navigate to project directory

                // Ensure Docker Compose is installed
                sh 'sudo docker ps'

                // Build and start containers
                sh '''
                    sudo docker compose down
                    sudo docker compose build
                    sudo docker compose up -d
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
