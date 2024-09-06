pipeline {
    agent any

    environment {
        STAGING_SERVER = 'Staging Server'
        PRODUCTION_SERVER = 'Production Server'
        RECIPIENT_EMAIL = 'hassaanbhai999.0@gmail.com'
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building the code using Gradle...'
                // Example: Build tool changed to Gradle.
            }
        }

        stage('Test') {
            steps {
                echo 'Running unit and integration tests using JUnit...'
                // Unit testing: JUnit or any other testing framework
            }
        }

        stage('Code Analysis') {
            steps {
                echo 'Performing static code analysis using Checkstyle...'
                // Example tool: Checkstyle for static analysis
            }
        }

        stage('Security Scan') {
            steps {
                echo 'Performing security scan using SonarQube...'
                // Security scan tool: SonarQube, or any other like Snyk
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo "Deploying the application to ${env.STAGING_SERVER}..."
                // Example: SCP or rsync for deployment
            }
        }

        stage('Run Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on the staging environment using Postman...'
                // Example tool: Postman, Selenium, or other API testing frameworks
            }
        }

        stage('Deploy to Production') {
            steps {
                echo "Deploying the application to ${env.PRODUCTION_SERVER}..."
                // Deployment method to Production server
            }
        }
    }

    post {
        success {
            emailext to: "${env.RECIPIENT_EMAIL}",
                subject: "Pipeline - Successful Build",
                body: "The pipeline has completed successfully."
        }

        failure {
            emailext to: "${env.RECIPIENT_EMAIL}",
                subject: "Pipeline - Failed Build",
                body: "The pipeline has failed. Please check the logs."
        }
    }
}

