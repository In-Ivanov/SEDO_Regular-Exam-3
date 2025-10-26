pipeline {
    agent any
    stages {
        stage("Restore Dependencies") {
            steps {
                bat "dotnet restore"
            }
        }

        stage("Build") {
            steps {
                bat "dotnet build --no-restore"
            }
        }

        stage("Run Unit and Integration Tests") {
            steps {
                bat "dotnet test --configuration Release --no-build --verbosity normal"
            }
        }
    }
}
