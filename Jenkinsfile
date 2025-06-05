pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t myapp:latest .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker rm -f myapp || true'
                sh 'docker run -d -p 5000:5000 --name myapp myapp:latest'
            }
        }
    }
}
