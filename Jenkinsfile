pipeline {
    agent any
 
    environment {
        GITHUB_CREDENTIALS = credentials('100122') // Use the credentials ID configured in Jenkins
    }
 
    stages {
        stage('Checkout') {
            steps {
                script {
                    git credentials: GITHUB_CREDENTIALS, url: 'https://github.com/Himaja2210/declarative.git', branch: 'main'
                }
            }
        }
 
        stage('Build') {
            steps {
                sh 'echo "Building application..."'
                sh './build.sh' // Adjust this to your build script
            }
        }
 
        stage('Test') {
            steps {
                sh 'echo "Running tests..."'
                sh './test.sh' // Adjust this to your test script
            }
        }
 
        stage('Deploy') {
            steps {
                sh 'echo "Deploying application..."'
                sh './deploy.sh' // Adjust this to your deploy script
            }
        }
    }
}
