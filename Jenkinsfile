pipeline {
    agent any

    stages {
        stage("Test") {
            steps {
                // Your test steps here
            }
            post {
                success {
                    emailext subject: "Test Stage Successful",
                        body: "The test stage completed successfully.",
                        to: "your.email@example.com",
                        attachLog: true
                }
                failure {
                    emailext subject: "Test Stage Failed",
                        body: "The test stage failed. Please check the logs for details.",
                        to: "your.email@example.com",
                        attachLog: true
                }
            }
        }

        stage("Security Scan") {
            steps {
                // Your security scan steps here
            }
            post {
                success {
                    emailext subject: "Security Scan Successful",
                        body: "The security scan completed successfully.",
                        to: "your.email@example.com",
                        attachLog: true
                }
                failure {
                    emailext subject: "Security Scan Failed",
                        body: "The security scan failed. Please check the logs for details.",
                        to: "your.email@example.com",
                        attachLog: true
                }
            }
        }
    }
}
