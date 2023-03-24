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
                sh ' docker build -t khanshoyeb7/fromjenkins . '
            }
        }
        stage('Push Docker Image') {
            steps {
                withCredentials([string(credentialsId: 'dockerpass', variable: 'dockerpasswd')]) {
                sh ' docker login -u khanshoyeb7 -p ${dockerpasswd}'
}
                sh ' docker push  khanshoyeb7/fromjenkins'
            }
        }
    }
}
