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
                //sh 'go mod init helloworld'
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
        stage('list') {  
            steps {
                sh 'ls -la ${GOPATH}'
            }
        }
        
        stage('login server'){
         steps{
            sshagent(credentials:['Login_Cloud_Server']){
               sh 'scp  -o StrictHostKeyChecking=no  ./main.go tinhuynh@34.142.187.195:~/'
          }
        echo "success lgoin"
         }
       }
    }
}
