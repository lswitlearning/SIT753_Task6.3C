pipeline {
    agent any

    stages {
        stage("Echo Environment Variable") {
            steps {
                sh "echo 'Hello World'"
            }
            post {
                success { 
                    emailext subject: "Build ${env.BUILD_NUMBER} Successful",
                        body: "Congratulations! Your build succeeded.",
                        to: "your.email@example.com"
                }
                unstable { 
                    emailext subject: "Build ${env.BUILD_NUMBER} Unstable",
                        body: "Your build is unstable.",
                        to: "your.email@example.com"
                }
                failure { 
                    emailext subject: "Build ${env.BUILD_NUMBER} Failed",
                        body: "Unfortunately, your build failed.",
                        to: "your.email@example.com"
                }
            }
        }
    }
}
