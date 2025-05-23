pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/kunalsk36/devopsprj.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                script {
                    sh 'docker build -t devops-blog .'
                }
            }
        }
        stage('Deploy using Ansible') {
            steps {
                script {
                    sh 'wsl ansible-playbook /home/myansibleprj/deploy.yml'
                }
            }
        }
    }
}
