pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building the project using Maven.'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests using JUnit and Selenium'
            }
            post {
                success {
                    emailext attachLog: true,
                    to: 'dharshinisungkur@gmail.com', 
                    subject: 'Integration Tests Status Email', 
                    body: 'Integration tests completed successfully'
                }
                failure {
                    emailext attachLog: true,
                    to: 'dharshinisungkur@gmail.com', 
                    subject: 'Build Status Email', 
                    body: 'integration tests failed'
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Analyzing code quality with SonarQube.'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Performing security scan using OWASP ZAP.'
            }
            post {
                success {
                    emailext attachLog: true,
                    to: 'dharshinisungkur@gmail.com', 
                    subject: 'Security scan Status Email', 
                    body: 'Security scan completed successfully' 
                }
                failure {
                    emailext attachLog: true,
                    to: 'dharshinisungkur@gmail.com', 
                    subject: 'Security scan Status Email', 
                    body: 'Security scan failed'
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying application to AWS EC2 staging environment.'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests in the staging environment.'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying application to AWS EC2 production server.'
            }
        }
    }
    post {
        success {
            emailext attachLog: true,
            to: 'dharshinisungkur@gmail.com', 
            subject: 'Pipeline Status Email', 
            body: 'Pipelin completed successfully'
        }
        failure {
            emailext attachLog: true,
            to: 'dharshinisungkur@gmail.com', 
            subject: 'Pipeline Status Email', 
            body: 'Pipeline failed'
        }
    }
}
