pipeline {
    agent any
    
    environment {
        // Define environment variables here
        MAVEN_HOME = tool 'Maven 3.8.1'  // Ensure Maven is installed in Jenkins
    }
    
    stages {
        stage('Checkout') {
            steps {
                echo 'Cloning the repository...'
                checkout scm
            }
        }
        
        stage('Build') {
            steps {
                echo 'Building the application...'
                script {
                    // Ensure Maven is available
                    sh "'${MAVEN_HOME}/bin/mvn' clean install" 
                }
            }
        }
        
        stage('Test') {
            steps {
                echo 'Running unit tests...'
                script {
                    // Run your tests here, for example with Maven:
                    sh "'${MAVEN_HOME}/bin/mvn' test"
                }
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                script {
                    // Add deployment commands here (e.g., copying files, executing scripts)
                    // For example:
                    // sh './deploy.sh'
                }
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
