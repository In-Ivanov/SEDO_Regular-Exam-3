pipeline {
    agent any

    triggers {
        pollSCM('H/5 * * * *') 
    }

    stages {
        stage('Build') {
            steps {
                bat 'dotnet build --configuration Release'
            }
        }

        stage('Test') {
            steps {
                bat 'dotnet test --verbosity normal'
            }
        }
    }
}
