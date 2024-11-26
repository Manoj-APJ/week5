pipeline {
    agent any

    tools {
        nodejs "NodeJS 18" // Ensure this matches the NodeJS configuration name in Jenkins
    }

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'master', url: 'https://github.com/shiv4j/week5.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                script {
                    // Install dependencies using npm
                    sh 'npm install'
                }
            }
        }

        stage('Run Tests') {
            steps {
                script {
                    // Run the tests using npm
                    sh 'npm test'
                }
            }
        }

        stage('Build') {
            steps {
                script {
                    // Run the build process using npm
                    sh 'npm run build'
                }
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                // Add deployment steps here, such as copying files to a server or running a deployment script.
            }
        }
    }

    post {
        success {
            echo 'Build and Deployment Successful!'
        }
        failure {
            echo 'Build or Deployment Failed!'
        }
    }
}
