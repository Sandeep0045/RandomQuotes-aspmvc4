pipeline {
    agent any
     triggers {
        githubPush()
      }
    stages {
        stage('Restore packages'){
           steps{
               sh 'nuget restore '
            }
         }        
        stage('Clean'){
           steps{
               sh 'nuget clean  --configuration Release'
            }
         }
        stage('Build'){
           steps{
               sh 'nuget build  --configuration Release --no-restore'
            }
         }
        stage('Publish'){
           steps{
               sh 'nuget publish  RandomQuotes.csproj --configuration Release --no-restore'
             }
        }
        
        
         
     
    }
}
