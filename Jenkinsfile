pipeline {
    agent any
    triggers {
        pollSCM('* * * * *')
    }
    environment {
        DIRECTORY_PATH = 'C:/Users/anjav/Documents/SIT753'
        TESTING_ENVIRONMENT = 'Staging Server (AWS EC2)'
        PRODUCTION_ENVIRONMENT = 'Anja Vukosavljevic'
    }
    stages {
        stage('Build') {
            steps {
                echo "Stage 1 - Build"
                echo "Using Maven to compile the source code from ${env.DIRECTORY_PATH} and package it into an artifact"
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo "Stage 2 - Unit and Integration Tests"
                echo "Running unit tests using JUnit to check individual components work correctly"
                echo "Running integration tests using Selenium to ensure components work together"
            }
        }
        stage('Code Analysis') {
            steps {
                echo "Stage 3 - Code Analysis"
                echo "Using SonarQube to analyse code quality and check it meets industry standards"
            }
        }
        stage('Security Scan') {
            steps {
                echo "Stage 4 - Security Scan"
                echo "Using OWASP Dependency-Check to scan for known vulnerabilities in dependencies"
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo "Stage 5 - Deploy to Staging"
                echo "Deploying application to staging environment: ${env.TESTING_ENVIRONMENT} using AWS CLI"
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo "Stage 6 - Integration Tests on Staging"
                echo "Running integration tests on staging using Postman to verify the application works in a production-like environment"
            }
        }
        stage('Deploy to Production') {
            steps {
                echo "Stage 7 - Deploy to Production"
                echo "Deploying application to production environment: ${env.PRODUCTION_ENVIRONMENT} using AWS CLI"
            }
        }
    }
}
