pipeline {
    agent any

    tools {
        maven 'Maven3'
        jdk 'JDK17'
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/viji-sarvesh/ciexpipeline.git'
            }
        }

        stage('Build') {
            steps {
                bat 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                bat 'mvn test'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                bat 'xcopy target\\*.jar C:\\deploy /Y'
            }
        }
    }

    post {
        always {
            echo 'Pipeline finished!'
        }
    }
}
