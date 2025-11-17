pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Malikidrees7613/DevOps_Assignment_No_1.git'
            }
        }

        stage('Test Pipeline') {
            steps {
                echo "Pipeline is running successfully!"
                sh "echo Hello from Jenkins Pipeline"
            }
        }
    }

    post {
        success {
            echo "Pipeline test completed successfully."
        }
        failure {
            echo "Pipeline test failed."
        }
    }
}
