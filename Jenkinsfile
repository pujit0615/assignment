pipeline {
    agent any

    stages {
        stage('Lint') {
            steps {
                sh 'npm run lint || true'
            }
        }
        stage('Test') {
            steps {
                sh 'npm test'
            }
        }
        stage('Build') {
            steps {
                sh 'docker build -t myapp:latest .'
            }
        }
        stage('Deploy') {
            steps {
                sh 'docker run -d -p 80:3000 --name myapp myapp:latest'
            }
        }
    }
}
