pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                echo 'Cloning portfolio repository...'
                git branch: 'main', url: 'https://github.com/Yogitha01/resume-portfolio.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Preparing build files...'
            }
        }

        stage('Test') {
            steps {
                echo 'Running HTML validation (optional)...'
                // Add test commands if you have them
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the portfolio website...'
                // Example for local deploy (adjust path if needed)
                sh '''
                    mkdir -p /var/www/html/portfolio
                    cp -r build/* /var/www/html/portfolio/
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
