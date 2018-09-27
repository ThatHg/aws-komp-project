pipeline {
    agent {
        docker {
            image 'alpine'
        }
    }
    environment {
        DOCKER_API_TOKEN = credentials('thathg-docker-cloud')
    }
    stages {
        stage('pre') {
            steps {
                echo 'fetching...'
            }
        }
        stage('test') {
            steps {
                echo 'testing'
            }
        }
        stage('build') {
            steps {
                echo 'building...'
                sh 'ls'
                sh 'find ./ -name docker*'
            }
        }
        stage('deploy') {
            steps {
                echo 'deploying...'
            }
        }
    }
}