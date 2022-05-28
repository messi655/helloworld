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
                sh '$GOPATH/bin/go test'
            }
        }
        stage('build') {
            steps {
                sh '$GOPATH/bin/go build'
            }
        }
        stage('release') {  
            steps {
                sh '$GOPATH/bin/go install'
            }
        }
    }
}
