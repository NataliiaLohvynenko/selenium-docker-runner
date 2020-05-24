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
    }
    post{
        always{
             archiveArtifacts artifacts: 'output/**'
             bat "docker-compose down"
        }
    }
}