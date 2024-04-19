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
            emailext
            body: "${currentBuild.currentResult}: Job ${env.JOB_NAME} build ${env.BUILD_NUMBER}\n More info at: ${env.BUILD_URL}"
            recipientProviders: [[$class: 'DevelopersRecipientProvider'] 
            [$class: 'RequesterRecipientProvider']]
            subject: "Jenkins Build ${currentBuild.currentResult}: Job ${env.JOB_NAME}"
            
        }
        failure {
            emailext(
                subject: "Test Status - ${BUILD_STATUS}",
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
