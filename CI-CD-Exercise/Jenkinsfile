pipeline {
    agent any

    environment {
        NODE_VERSION = '18.x'
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Setup Node.js') {
            steps {
                script {
                    // Install Node.js 18.x using nvm
                    sh 'curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash'
                    sh '. ~/.nvm/nvm.sh && nvm install $NODE_VERSION && nvm use $NODE_VERSION'
                }
            }
        }
        stage('Install dependencies') {
            steps {
                sh 'npm install'
            }
        }
        stage('Start the app') {
            steps {
                sh 'npm start &'
            }
        }
        stage('Run tests') {
            steps {
                sh 'npm test'
            }
        }
    }
}
