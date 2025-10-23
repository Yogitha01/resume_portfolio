pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                echo 'Cloning portfolio repository...'
                git branch: 'main', url: 'https://github.com/Yogitha01/resume_portfolio.git'
            }
        }

        stage('Verify Files') {
            steps {
                echo 'Listing project files...'
                bat 'dir'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the portfolio website...'
                // Adjust destination path as needed
                bat '''
                if not exist C:\\Users\\Public\\portfolio mkdir C:\\Users\\Public\\portfolio
                xcopy /s /y * C:\\Users\\Public\\portfolio\\
                '''
            }
        }
    }

    post {
        success {
            echo '✅ Portfolio deployed successfully!'
        }
        failure {
            echo '❌ Build failed. Check logs for details.'
        }
    }
}
