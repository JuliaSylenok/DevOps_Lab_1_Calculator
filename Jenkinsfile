
pipeline {
    agent any

    stages {
        stage('Restore') {
            steps {
                echo 'Restoring NuGet packages...'
                bat 'dotnet restore Lab_1_Calculator.sln'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the project...'
                bat 'dotnet build Lab_1_Calculator.sln --configuration Release'
            }
        }

        stage('Test') {
            steps {
                echo 'Running unit tests...'
                bat 'dotnet test Tests/Tests.csproj --configuration Release'
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
