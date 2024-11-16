pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                checkout scm
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }
        stage('Test') {
            steps {
                sh 'echo "Running tests"'
            }
        }
        stage('Deploy') {
            steps {
                sh 'echo "Deploying application"'
            }
        }
    }
    post {
        always {
            echo 'Pipeline execution complete.'
        }
        success {
            echo 'Pipeline succeeded.'
        }
        failure {
            echo 'Pipeline failed.'
        }
    }
}
