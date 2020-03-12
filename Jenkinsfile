/**
 * This pipeline describes a multi container job
 */

podTemplate(yaml: """
apiVersion: v1
kind: Pod
spec:
  containers:
  - name: node
    image: node:12
    command: ['cat']
    tty: true
  - name: aws-cli
    image: mesosphere/aws-cli
    command: ['cat']
    tty: true
"""
  ) {

  node(POD_LABEL) {
    stage('NodeJS stuff') {
      container('node') {
        sh 'npm --version'
        sh 'mkdir my_other_dir'
        sh 'yarn --version'
      }
    }

    stage('AWS cli') {
      container('aws-cli') {
        sh """
        aws --version
        ls -lah
        echo 'hello'
        """
      }
    }

  }
}
