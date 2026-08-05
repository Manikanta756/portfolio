pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                    sudo rm -rf /usr/share/nginx/html/*
                    sudo cp -r ./* /usr/share/nginx/html/
                '''
            }
        }

        stage('Verify') {
            steps {
                sh 'ls -la /usr/share/nginx/html'
            }
        }
    }
}
