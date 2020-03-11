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
"""
  ) {

  node(POD_LABEL) {
    stage('NodeJS stuff') {
      container('node') {
        sh 'npm --version'
      }
    }

    stage('Other part') {
      container('node') {
        sh """
        echo 'hello'
        """
      }
    }

  }
}
