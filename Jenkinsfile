pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git 'https://github.com/venkatbhaskar/jenkins-demo.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    docker.build('jenkins-demo-image')
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                script {
                    sh 'docker run -d -p 5000:5000 jenkins-demo-image'
                }
            }
        }
    }
}

