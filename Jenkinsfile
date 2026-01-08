pipeline {
    agent any

    tools {
        maven 'Default-Maven'  // Must be pre-configured in Jenkins Global Tools
        jdk 'OpenJDK11'     // Must be pre-configured in Jenkins Global Tools
    }

    stages {
        stage('Build') {
            steps {
                bat 'mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                bat 'mvn test'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }

        stage('Deploy') {
            steps {
                bat 'echo "Deploying application... (simulated)"'
                // In real use: deploy to server, Docker, etc.
            }
        }
    }

    post {
        always {
            cleanWs()  // Clean workspace after build (requires Workspace Cleanup Plugin)
        }
    }
}