pipeline {
    agent any
    stages {
        stage('Starting Grid') {
            steps {
                bat "docker-compose up -d hub chrome firefox"
            }
        }
        stage('Running test') {
            steps {
                        bat "docker-compose up search-module book-flight-module"
            }
        }
        stage('Bring build down') {
            steps {
                bat "docker-compose down"
            }
        }
    }
}