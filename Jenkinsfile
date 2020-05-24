pipeline {
    agent any
    stages {
        stage('Pull Latest Image') {
                steps {
                    bat "docker-pull lohvynen/selenium-docker"
                }
            }
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