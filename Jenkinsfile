pipeline {
    agent any
    stages {
        stage('Install dependencies') {
            steps {
                bat 'npm install'
            }
        }
        stage('Test') {
            parallel {
                stage('Run audit tests') {
                    steps {
                        bat 'npm audit'
                    }
                }
                stage('Run tests') {
                    steps {
                        bat 'npm test'
                    }
                }
            }
        }
    }
}