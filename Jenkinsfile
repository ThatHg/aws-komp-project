pipeline {
    agent {
        docker {
            image 'alpine'
        }
    }
    environment {
        DOCKER_API_TOKEN: cridentials('thathg-docker-cloud')
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
                echo $(ls)
            }
        }
        stage('deploy') {
            steps {
                echo 'deploying...'
            }
        }
    }
}