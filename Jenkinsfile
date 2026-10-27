pipeline {
    agent any
    tools{
        maven 'Maven-3.9.16',
        jdk 'JDK-21'
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/adharsh-04/practice-notes.git'
            }
        }

        stage('Build JAR') {
            steps {
                sh 'mvn clean package -DskipTests'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t notes-app .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 8080:8080 notes-app'
            }
        }
    }
}
