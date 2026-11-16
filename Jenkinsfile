pipeline {
    agent any

    triggers {
        githubPush()
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
                echo 'College Website code downloaded successfully'
            }
        }

        stage('Build') {
            steps {
                bat 'echo Building College Website'
                bat 'dir'
                echo 'Build completed successfully'
            }
        }

        stage('Test') {
            steps {
                bat 'if not exist index.html exit /b 1'
                bat 'if not exist style.css exit /b 1'
                echo 'Website file validation successful'
            }
        }

        stage('Deploy') {
            steps {
                echo 'College Website is ready for deployment'
            }
        }
    }

    post {
        success {
            echo 'PIPELINE EXECUTED SUCCESSFULLY'
        }
        failure {
            echo 'PIPELINE EXECUTION FAILED'
        }
    }
}
