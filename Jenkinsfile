pipeline {
    agent any
    tools {
        go 'go1.18'
    }
    environment {
        GO118MODULE = 'on'
    }
    stages {
        stage('test') {
            steps {
                sh 'go mod init'
                sh 'go test'
            }
        }
        stage('build') {
            steps {
                sh 'go build'
            }
        }
        stage('release') {  
            steps {
                sh 'go install'
            }
        }
    }
}
