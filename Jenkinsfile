pipeline {
    agent any
    stages {
      stage('Test') {
          steps {
              echo 'hello world'
              sh 'ls'
              input 'this is an input'
          }
      }
    }
      post {
          success {
              slackSend channel: '#lambda-notifications',
                        color: 'good',
                        message: "The pipeline ${currentBuild.fullDisplayName} completed successfully."
          }
      }
}

