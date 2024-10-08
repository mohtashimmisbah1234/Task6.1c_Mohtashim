pipeline {
    agent any
    
    environment {
        EMAIL_RECIPIENT = 'mohtashimmisbah1234@gmail.com'
    }
    
    stages {
        stage('Build') {
            steps {
                script {
                    echo 'Building the code...'
                    // Tool: Maven
                }
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                script {
                    echo 'Running unit and integration tests...'
                    // Tool: JUnit or TestNG
                }
            }
        }
        stage('Code Analysis') {
            steps {
                script {
                    echo 'Analyzing code...'
                    // Tool: SonarQube
                }
            }
        }
        stage('Security Scan') {
            steps {
                script {
                    echo 'Performing security scan...'
                    // Tool: OWASP ZAP
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                script {
                    echo 'Deploying to staging server...'
                    // Tool: AWS CLI
                }
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                script {
                    echo 'Running integration tests on staging...'
                    // Tool: Selenium or Postman
                }
            }
        }
        stage('Deploy to Production') {
            steps {
                script {
                    echo 'Deploying to production server...'
                    // Tool: AWS CLI
                }
            }
        }
    }
    
    post {
        success {
            script {
                echo 'Pipeline succeeded!'
                emailext to: "${EMAIL_RECIPIENT}",
                         subject: "Jenkins Pipeline Success",
                         body: "The pipeline completed successfully.",
                         attachmentsPattern: "**/build.log", 
                         mimeType: 'text/plain',
                         attachLog: true
            }
        }
        failure {
            script {
                echo 'Pipeline failed!'
                emailext to: "${EMAIL_RECIPIENT}",
                         subject: "Jenkins Pipeline Failure",
                         body: "The pipeline has failed. Check the logs for details.",
                         attachmentsPattern: "**/build.log",  
                         mimeType: 'text/plain',
                         attachLog: true
            }
        }
    }
}
