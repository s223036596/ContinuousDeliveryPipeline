pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo "Using maven to build the code"
            }
            post {
                success {
                    archiveArtifacts artifacts: '**/*.log', fingerprint: true  // Archive log files
                    mail to: "maryam.khazaeepool@gmail.com",
                         subject: "Build Status Email",
                         body: "Build was successful. Log files are available at: ${BUILD_URL}/artifact/"
                }
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo "Using JUnit for Unit and Integration Testing."
            }
        }

        stage('Code Analysis') {
            steps {
                echo "Use tools like SonarQube for code analysis"
            }
        }

        stage('Security Scan') {
            steps {
                echo "Using OWASP ZAP for security scanning"
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo "Using tools like AWS CLI to deploy to staging server"
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo "Using Selenium to run integration tests on staging"
            }
        }

        stage('Deploy to Production') {
            steps {
                echo "Using AWS CLI to deploy to a production server"
            }
        }
    }
}
