pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Build using Maven'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Run unit tests using JUnit and integration tests with Mocha'
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Static code analysis using ESLint'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Security scan with npm audit'
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to AWS EC2 staging server'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running staging tests using Postman'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to production server on AWS EC2'
            }
        }
    }
    post {
    success {
        emailext (
            subject: "Build Successful: ${env.JOB_NAME} [#${env.BUILD_NUMBER}]",
            body: "Good job! The build completed successfully.",
            to: 'binarasadunsha22774@gmail.com'
        )
    }
    failure {
        emailext (
            subject: "Build Failed: ${env.JOB_NAME} [#${env.BUILD_NUMBER}]",
            body: "Something went wrong. Please check the build log.",
            to: 'binarasadunsha22774@gmail.com'
        )
    }
}

}
