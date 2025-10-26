pipeline {
    agent any

    triggers {
        pollSCM('H/5 * * * *')

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Restore') {
            steps {
                bat 'dotnet restore'
            }
        }

        stage('Build') {
            steps {
                bat 'dotnet build --configuration Release'
            }
        }

        stage('Test') {
            steps {
                bat 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}
