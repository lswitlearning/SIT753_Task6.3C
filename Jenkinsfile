pipeline{
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


                mail bcc: '', body: 'Test stage completed.\n\nLogs attached.', subject: 'Test Status123 - ' $BUILD_STATUS, to: 'lswitlearning@gmail.com'
            }

        }
        
        
 
        
        stage('Code Analysis') {
            steps {
                echo "Integrate a code analysis tool to analyse the code using SonarQube"
            }
        }
        stage('Security Scan') {
            steps {
                echo "Perform a security scan on the code using OWASP Dependency-Check"
                }
            }
            
        stage('Deploy to Staging') {
            steps {
                echo "deploy the application to Azure Virtual Machines"
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo "Run integration tests on the staging environment"
            }
        }
        stage('Deploy to Production') {
            steps {
                echo "deploy the application to a production server Azure Virtual Machines"
        }
    }
}
}
