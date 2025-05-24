pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                bat 'docker build -t devops-blog .'
            }
        }

        stage('Run Docker Container') {
            steps {
                bat '''
                docker rm -f devops-blog || exit 0
                docker run -d -p 8080:80 --name devops-blog devops-blog
                '''
            }
        }
    }
}
