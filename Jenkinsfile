pipeline {
    agent any

    stages {
        stage('Stage 1: Build') {
            steps {
                echo 'Build the code using a build automation tool like Maven to compile and package the code.'
            }
        }

        stage('Stage 2: Unit and Integration Tests') {
            steps {
                echo 'Run unit tests using a tool like JUnit and integration tests using a tool like Selenium.'
            }
            post {
                success {
                    emailext subject: "Unit and Integration Tests Passed",
                              body: "The Unit and Integration Tests stage passed successfully.",
                              to: "maryam.khazaeepool@gmail.com",
                              attachmentsPattern: '**/build.log'
                }
            }
        }

        stage('Stage 3: Code Analysis') {
            steps {
                echo 'Integrate a code analysis tool like SonarQube to analyze the code and ensure it meets industry standards.'
            }
        }

        stage('Stage 4: Security Scan') {
            steps {
                echo 'Perform a security scan on the code using a tool like OWASP ZAP to identify vulnerabilities.'
            }
            post {
                success {
                    emailext subject: "Security Scan Passed",
                              body: "The Security Scan stage passed successfully.",
                              to: "maryam.khazaeepool@gmail.com",
                              attachmentsPattern: '**/build.log'
                }
            }
        }

        stage('Stage 5: Deploy to Staging') {
            steps {
                echo 'Deploy the application to a staging server like an AWS EC2 instance.'
            }
        }

        stage('Stage 6: Integration Tests on Staging') {
            steps {
                echo 'Run integration tests on the staging environment using a tool like Selenium to ensure the application functions as expected in a production-like environment.'
            }
        }

        stage('Stage 7: Deploy to Production') {
            steps {
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

