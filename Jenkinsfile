pipeline {
    agent any

    stages {
        stage('Docker Socket') {
            steps {
                sh 'sudo chmod 666 /var/run/docker.sock '
            }
        }
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
