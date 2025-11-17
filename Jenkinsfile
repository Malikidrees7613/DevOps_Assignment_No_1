pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                echo 'Pulling code from GitHub...'
                git branch: 'main', url: 'https://github.com/Malikidrees7613/DevOps_Assignment_No_1.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                echo 'Installing project dependencies...'
                sh 'npm install'
            }
        }

        stage('Build Project') {
            steps {
                echo 'Building the web project...'
                sh 'npm run build'
            }
        }

        stage('Run Tests') {
            steps {
                echo 'Running tests...'
                sh 'npm test'
            }
        }

        stage('Deployment') {
            steps {
                echo 'Deploying the web project...'
                // Example for copying build files to server directory
                // Adjust according to your deployment method
                sh 'cp -r dist/* /var/www/html/'
            }
        }
    }

    post {
        success {
            echo 'Build and deployment completed successfully!'
        }
        failure {
            echo 'Build failed. Please check the error logs.'
        }
    }
}
