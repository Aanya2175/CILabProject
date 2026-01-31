pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            when { branch 'main' }
            steps {
                bat 'mvn clean package'
            }
        }

        stage('Test') {
            when {
                anyOf {
                    branch 'main'
                    expression { env.BRANCH_NAME.startsWith('feature/') }
                    expression { env.BRANCH_NAME.startsWith('release/') }
                }
            }
            steps {
                bat 'mvn test'
            }
        }

        stage('Security Scan (Release)') {
            when {
                expression { env.BRANCH_NAME.startsWith('release/') }
            }
            steps {
                echo "Running security scan (dummy)..."
                bat 'echo Security scan complete'
            }
        }

        stage('Archive Artifacts') {
            when { branch 'main' }
            steps {
                archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
            }
        }
    }

    post {
        always {
            junit 'target/surefire-reports/*.xml'
        }
    }
}
