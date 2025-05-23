pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t devops-blog .'
            }
        }

        stage('Deploy using Ansible') {
            steps {
                bat 'wsl ansible-playbook /home/myansibleprj/deploy.yml'
            }
        }
    }
}
