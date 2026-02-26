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
                sh 'cd $WORKSPACE'

                // Ensure Docker Compose is installed
                sh 'docker ps'

                // Build and start containers
                sh '''
                    docker compose down
                    docker compose build
                    docker compose up -d
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
