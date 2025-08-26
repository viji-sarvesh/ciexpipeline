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
        echo "Running the JAR from target folder..."
        bat "java -jar target\\*.jar"
    }
}

    }

    post {
        always {
            echo 'Pipeline finished!'
        }
    }
}
