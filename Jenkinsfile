node {
      stage('Test') {
          echo 'hello world'
          sh 'ls'
          input 'this is an input'
      }
      post {
          success {
              slackSend channel: '#lambda-notifications',
                        color: 'good',
                        message: "The pipeline ${currentBuild.fullDisplayName} completed successfully."
          }
      }
}

