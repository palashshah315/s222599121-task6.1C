pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo '--- Building the code ---'
                echo 'Building MVN...'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo '--- Running unit and integration tests with jenkins ---'
                echo 'Running Maven tests...'
            }
            post {
                success {
                    echo '--- Tests Succeeded with jenkins---'
                    emailext subject: 'Tests Completed - Success',
                             body: 'Unit and integration tests have completed successfully.\n\n${BUILD_LOG, maxLines=1000}',
                             to: 'palashshah345@gmail.com',
                             attachLog: true
                }
                failure {
                    echo '--- Tests Failed ---'
                    emailext subject: 'Tests Completed - Failure',
                             body: 'Unit and integration tests have failed.\n\n${BUILD_LOG, maxLines=1000}',
                             to: 'palashshah345@gmail.com',
                             attachLog: true
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo '--- Performing code analysis with jenkins ---'
                echo 'Performing code analysis...'
            }
        }
        stage('Security Scan') {
            steps {
                echo '--- Performing security scan ---'
                echo 'Performing security scan...'
            }
            post {
                success {
                    echo '--- Security Scan Succeeded ---'
                    emailext subject: 'Security Scan Completed - Success',
                             body: 'Security scan has completed successfully.\n\n${BUILD_LOG, maxLines=1000}',
                             to: 'palashshah345@gmail.com',
                             attachLog: true
                }
                failure {
                    echo '--- Security Scan Failed ---'
                    emailext subject: 'Security Scan Completed - Failure',
                             body: 'Security scan has failed.\n\n${BUILD_LOG, maxLines=1000}',
                             to: 'palashshah345@gmail.com',
                             attachLog: true
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo '--- Deploying to staging environment ---'
                echo 'Deploying to staging environment...'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo '--- Running integration tests on staging environment ---'
                echo 'Running integration tests on staging environment...'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo '--- Deploying to production environment ---'
                echo 'Deploying to production environment...'
            }
        }
    }
    post {
        success {
            echo '--- Pipeline Successful ---'
        }
        failure {
            echo '--- Pipeline Failed ---'
        }
    }
}
