pipeline {
    agent any

    triggers {
        pollSCM('* * * * *')
    }

    environment {
        DIRECTORY_PATH = 'Jenkins-CI-Pipeline'
        TESTING_ENVIRONMENT = 'Staging'
        PRODUCTION_ENVIRONMENT = 'Rahul'
    }

    stages {

        stage('Build') {
            steps {
                echo 'Stage 1: Build'
                echo 'Task: Compile and package the application code.'
                echo 'Tool: Maven can be used as the build automation tool.'
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo 'Stage 2: Unit and Integration Tests'
                echo 'Task: Run unit tests and integration tests to verify application functionality.'
                echo 'Tools: JUnit, Selenium, or Jest can be used for test automation.'
            }
        }

        stage('Code Analysis') {
            steps {
                echo 'Stage 3: Code Analysis'
                echo 'Task: Perform static code analysis to identify bugs and vulnerabilities.'
                echo 'Tool: SonarQube can be used for code quality checks.'
            }
        }

        stage('Security Scan') {
            steps {
                echo 'Stage 4: Security Scan'
                echo 'Task: Scan dependencies and source code for security vulnerabilities.'
                echo 'Tool: OWASP Dependency-Check or Snyk can be used.'
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'Stage 5: Deploy to Staging Environment'
                echo "Deploying application to ${TESTING_ENVIRONMENT} environment."
            }
        }

        stage('Approval') {
            steps {
                echo 'Stage 6: Approval'
                echo 'Waiting for manual approval before production deployment.'
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Stage 7: Deploy to Production Environment'
                echo "Deploying application to ${PRODUCTION_ENVIRONMENT} environment."
            }
        }
    }

    post {
        always {
            echo 'Pipeline execution completed.'
        }

        success {
            echo 'Pipeline executed successfully.'
        }

        failure {
            echo 'Pipeline execution failed.'
        }
    }
}
