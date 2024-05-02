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
                echo 'Running unit and integration tests using JUnit and Selenium.'
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
            mail to: 'dharshinisungkur@gmail.com', 
            subject: 'Build Status Email', 
            body: 'Stage completed successfully'
        }
        failure {
            mail to: 'dharshinisungkur@gmail.com', 
            subject: 'Build Status Email', 
            body: 'Stage failed'
        }
    }
}
