pipeline {
    agent any

    stages {
        stage('Pull Code') {
            steps {
                git 'https://github.com/GPBankar/HELLOWORLDD.git'
            }
        }

        stage('Compile') {
            steps {
                sh 'javac HelloWorld.java'
            }
        }

        stage('Execute') {
            steps {
                sh 'java HelloWorld'
            }
        }
    }
}
