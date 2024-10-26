pipeline{
    agent any
    stages {
        stage("Install dependencies") {
            steps {
                bat "npm install"
            }
        }
        stage("Test") {
            parallel {
                stage("Run audit tests") {
                    bat "npm audit"
                }
                stage("Run tests") {
                    bat "npm test"
                }
            }
        }
    }
}