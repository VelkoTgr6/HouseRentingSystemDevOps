pipeline {
    agent any

    stages {
        stage('Restore') {
            steps {
                script {
                    echo 'Restoring NuGet packages...'
                    bat 'dotnet restore'
                }
            }
        }

        stage('Build') {
            steps {
                script {
                    echo 'Building the project...'
                    bat 'dotnet build --no-restore'
                }
            }
        }
		
        stage('Test') {
            steps {
                script {
                    echo 'Running tests...'
                    bat 'dotnet test --no-build --verbosity normal'
                }
            }
        }
    }
}