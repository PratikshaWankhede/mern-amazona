pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                git 'https://github.com/PratikshaWankhede/mern-amazona.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t pratikshawankhede/amazona-app:latest ./backend'
            }
        }

        stage('Push Docker Image') {
            steps {
                withCredentials([usernamePassword(
                    credentialsId: 'dockerhub-creds',
                    usernameVariable: 'DOCKER_USER',
                    passwordVariable: 'DOCKER_PASS'
                )]) {

                    sh '''
                    echo $DOCKER_PASS | docker login -u $DOCKER_USER --password-stdin
                    docker push pratikshawankhede/amazona-app:latest
                    '''
                }
            }
        }
    }
}