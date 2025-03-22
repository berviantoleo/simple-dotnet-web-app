pipeline {
    agent any
    stages {
        stage('Build') { // <1>
            steps {
                sh 'dotnet restore' // <2>
                sh 'dotnet build --no-restore' // <3>
            }
        }
    }
}