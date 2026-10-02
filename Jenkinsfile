pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Restore') {
            steps {
                bat 'dotnet restore Lab_1_Calculator.sln'
            }
        }

        stage('Build') {
            steps {
                bat 'dotnet build Lab_1_Calculator.sln --no-restore'
            }
        }

        stage('Test') {
            steps {
                bat 'dotnet test Tests/Tests.csproj --no-build'
            }
        }
    }

    post {
        success {
            echo 'Build and tests completed successfully.'
        }

        failure {
            echo 'Build or tests failed.'
        }
    }
}