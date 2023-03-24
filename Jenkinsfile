pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                sh ' docker build -t ubuntu/khanshoyeb7 . '
            }
        }
        stage('Push Docker Image') {
            steps {
                withCredentials([string(credentialsId: 'dockerpass', variable: 'dockerpasswd')]) {
                sh ' docker login -u khanshoyeb7 -p ${dockerpasswd}'
}
                sh ' docker push  ubuntu/khanshoyeb7'
            }
        }
    }
}
