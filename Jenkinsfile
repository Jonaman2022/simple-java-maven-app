pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                bat 'mvn clean package'  // For Windows (use `sh` for Linux)
            }
        }
        stage('Test') {
            steps {
                bat 'mvn test'          // Runs tests and generates JUnit reports
            }
            post {
                always {
                    junit 'target/surefire-reports/**/*.xml'  // Path to test reports
                }
            }
        }
    }
}