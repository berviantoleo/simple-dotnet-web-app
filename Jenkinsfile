pipeline {
    agent any
    stages {
        stage('Build') { // <1>
            steps {
                sh 'dotnet restore' // <2>
                sh 'dotnet build --no-restore' // <3>
            }
        }
        stage('Test') {
            steps {
                sh 'dotnet test --no-build --no-restore --collect "XPlat Code Coverage"'
            }
            post {
                always {
                    recordCoverage(tools: [[parser: 'COBERTURA', pattern: '**/*.xml']], sourceDirectories: [[path: 'SimpleWebApi.Test/TestResults']])
                }
            }
        }
    }
}