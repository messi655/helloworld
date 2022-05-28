pipeline {
    agent any
    
    stages {
        stage('test') {
            steps {
                sh 'go test'      
            }
        }
        stage('build') {
            steps {
                sh 'cd ${GOPATH}/src'
                sh 'go build'
            }
        }
        stage('release') {  
            steps {
                sh '$GOPATH/bin/go install'
            }
        }
    }
}
