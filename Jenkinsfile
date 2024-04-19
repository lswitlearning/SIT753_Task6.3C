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
            emailext(
                subject: "Test Status - ${currentBuild.result}",
                body: "Test stage completed successfully.",
                to: "lswitlearning@gmail.com",
                attachmentsPattern: '**/*.pdf'
            )
        }
        failure {
            emailext(
                subject: "Test Status - ${currentBuild.result}",
                body: "Test stage failed.\n\nLogs attached.",
                to: "lswitlearning@gmail.com",
                attachmentsPattern: '**/*.pdf'
            )
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
