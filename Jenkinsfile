pipeline {
    agent any
    tools {
        go 'go1.18'
    }
    environment {
        GO118MODULE = 'on'
        CGO_ENABLED = 0 
        GOPATH = "${JENKINS_HOME}/jobs/${JOB_NAME}/builds/${BUILD_ID}"
    }
    
    stages {
        stage('test') {
            steps {
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
