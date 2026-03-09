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
sh 'docker build -t pratikshawankhede/amazona-app ./backend'
 }
 }

 stage('Push Docker Image') {
 steps {
 sh 'docker push pratikshawankhede/amazona-app'
 }
 }

 }

}