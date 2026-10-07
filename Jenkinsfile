pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/Adh1thiadev/devops-virtual-lab2.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t devops-lab:v1 .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d --name devops-container -p 8081:80 devops-lab:v1 || true'
            }
        }
    }
}
