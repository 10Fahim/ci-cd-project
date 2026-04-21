pipeline {
    agent any
    environment {
        DOCKER_IMAGE = "10fahimansari/cicd-app"
    }
    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'git@github.com:10Fahim/ci-cd-project.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $DOCKER_IMAGE .'
            }
        }
        stage('Login to DockerHub') {
            steps {
                withCredentials([usernamePassword(
                    credentialsId: 'dockerhub-cred',
                    usernameVariable: 'USER',
                    passwordVariable: 'PASS')]) {
                    sh 'echo $PASS | docker login -u $USER --password-stdin'
                }
            }
        }
        stage('Push Docker Image') {
            steps {
                sh 'docker push $DOCKER_IMAGE'
            }
        }
        stage('Deploy') {
            steps {
                sh '''
                    docker stop cicd-app || true
                    docker rm cicd-app || true
                    docker run -d --name cicd-app -p 5001:5000 $DOCKER_IMAGE
                '''
            }
        }
    }
}
