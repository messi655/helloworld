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
                // Create our project directory.
                sh 'cd ${GOPATH}/src'
                sh 'mkdir -p ${GOPATH}/src/hello-world'
                // Copy all files in our Jenkins workspace to our project directory.                
                sh 'cp -r ${WORKSPACE}/* ${GOPATH}/src/hello-world'
                // Build the app.
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
