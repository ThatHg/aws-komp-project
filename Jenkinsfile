pipeline {
    agent {
        docker {
            image 'alpine'
            label 'komp-general'
            args '-v /tmp:/tmp'
        }
    }
    environment {
        DOCKER_API_TOKEN = credentials('thathg-docker-cloud')
    }
    stages {
        stage('waiting for docker') {
            steps {
                echo '========== WAITING FOR DOCKER =========='
                sh './docker-wait'
            }
        }
        stage('pre') {
            steps {
                echo '========== PRE INFO =========='
                echo '== Docker Images =='
                sh 'docker image ls -a'
                echo '== Docker Containers =='
                sh 'docker container ls -a'
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
        stage('post') {
            steps {
                echo '========== POST INFO =========='
                echo '== Docker Images =='
                sh 'docker image ls -a'
                echo '== Docker Containers =='
                sh 'docker container ls -a'
            }
        }
    }
}