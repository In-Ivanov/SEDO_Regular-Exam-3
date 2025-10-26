pipeline {
    agent any

    triggers {
        pollSCM('H/5 * * * *') 
    }
    stages{
        stage("Restore the dependencies"){
            steps{
                bat "dotnet restore"
            }  
        }
        stage("Build"){
            steps{
                bat "dotnet build --no-restore"
            }
        }
        stage("Run Unit and Integration Test"){
            steps{
                bat "dotnet test --configuration Release --no-build --verbosity normal"
            }
        }
    }
  }