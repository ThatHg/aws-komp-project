pipeline {
    agent any
    environment {
        DOCKER_API_TOKEN = credentials('thathg-docker-cloud')
    }
    stages {
        stage('test') {
            steps {
                echo '========== TESTING =========='
            }
        }
        stage('build') {
            steps {
                echo '========== BUILDING =========='
                sh './docker-build'
            }
        }
        stage('deploy') {
            steps {
                echo '========== DEPLOYING =========='
                sh './docker-deploy thathg ${DOCKER_API_TOKEN}'
            }
        }
    }
}