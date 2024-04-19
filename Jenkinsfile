pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                echo "Build the code using Maven"
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo "Run unit tests using JUnit"
                echo "Run integration tests using Selenium"
            }
            post {
                success {
                    script {
                        emailext (
                            subject: "Unit and Integration Tests - Success",
                            body: "Unit and Integration Tests stage completed successfully.",
                            to: "lswitlearning@example.com",
                            attachLog: true,
                            attachmentsPattern: "**/*.pdf" // Attach PDF log files
                        )
                    }
                }
                failure {
                    script {
                        emailext (
                            subject: "Unit and Integration Tests - Failure",
                            body: "Unit and Integration Tests stage failed. Please check the logs for details.",
                            to: "lswitlearning@example.com",
                            attachLog: true,
                            attachmentsPattern: "**/*.pdf" // Attach PDF log files
                        )
                    }
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo "Integrate a code analysis tool to analyse the code using SonarQube"
            }
        }
    }
}
