pipeline {
    agent any

    stages {
        stage('Build Java App') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t my-java-app .'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh 'docker run --name my-java-container -d my-java-app'
            }
        }

        stage('Verify Container Output') {
            steps {
                sh 'docker logs my-java-container'
            }
        }

        stage('Cleanup') {
            steps {
                sh 'docker stop my-java-container || true'
                sh 'docker rm my-java-container || true'
            }
        }
    }
}
