pipeline {
    agent any

    stages {
        stage('Restore') {
            steps {
                script {
                    echo 'Restoring NuGet packages...'
                    sh 'dotnet restore'
                }
            }
        }

        stage('Build') {
            steps {
                script {
                    echo 'Building the project...'
                    sh 'dotnet build --no-restore'
                }
            }
        }
		
        stage('Test') {
            steps {
                script {
                    echo 'Running tests...'
                    sh 'dotnet test --no-build --verbosity normal'
                }
            }
        }
    }
}