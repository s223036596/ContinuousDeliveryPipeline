pipeline {
    agent any
    stages {
        stage('Stage 1: Build') {
            steps {
                // Build steps go here!
                echo 'Build the code using a build automation tool like Maven to compile and package the code.'
            }
            post {
                always {
                    script {
                        // Capture stage logs
                        def logFile = "build.log"
                        writeFile file: logFile, text: currentBuild.rawBuild.getLog(1000)

                        // Send email notification with logs attached
                        emailext attachLog: true, body: "The Stage 1: Build completed.", subject: "Build Completed", to: "maryam.khazaeepool@gmail.com", attachmentsPattern: "${logFile}"
                    }
                }
            }
        }
        stage('Stage 2: Unit and Integration Tests') {
            steps {
                // Test steps go here
                echo 'Run unit tests using a tool like JUnit and integration tests using a tool like Selenium.'
            }
            post {
                always {
                    script {
                        // Capture stage logs
                        def logFile = "test.log"
                        writeFile file: logFile, text: currentBuild.rawBuild.getLog(1000)

                        // Send email notification with logs attached
                        emailext attachLog: true, body: "The Stage 2: Unit and Integration Tests completed.", subject: "Unit and Integration Tests Completed", to: "maryam.khazaeepool@gmail.com", attachmentsPattern: "${logFile}"
                    }
                }
            }
        }
        stage('Stage 3: Code Analysis') {
            steps {
                // Code analysis steps go here
                echo 'Integrate a code analysis tool like SonarQube to analyze the code and ensure it meets industry standards.'
            }
        }
        stage('Stage 4: Security Scan') {
            steps {
                // Security scan steps go here
                echo 'Perform a security scan on the code using a tool like OWASP ZAP to identify vulnerabilities.'
            }
        }
        stage('Stage 5: Deploy to Staging') {
            steps {
                // Staging deployment steps go here
                echo 'Deploy the application to a staging server like an AWS EC2 instance.'
            }
        }
        stage('Stage 6: Integration Tests on Staging') {
            steps {
                // Staging integration test steps go here
                echo 'Run integration tests on the staging environment using a tool like Selenium to ensure the application functions as expected in a production-like environment.'
            }
        }
        stage('Stage 7: Deploy to Production') {
            steps {
                // Production deployment steps go here
                echo 'Deploy the application to a production server like an AWS EC2 instance.'
            }
        }
    }
    post {
        success {
            echo 'Pipeline completed successfully'
        }
        failure {
            echo 'Pipeline failed'
        }
    }
}

