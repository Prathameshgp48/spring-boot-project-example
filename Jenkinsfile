pipeline {
    agent any

    tools {
        maven 'M3'
    }

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build & Test') {
            steps {
                sh 'mvn clean test'
            }
        }

        stage('Package') {
            steps {
                sh 'mvn package'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploy artifact'
                sh 'mkdir -p /tmp/springboot-deploy'
                sh 'cp target/*.jar /tmp/springboot-deploy/'
            }
        }

    }
}
