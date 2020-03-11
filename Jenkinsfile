pipeline {
   agent any
   environment {
       registry = "magalixcorp/k8scicd"
       GOCACHE = "/tmp"
   }
   stages {
       stage('Build') {
           agent {
               docker {
                   image 'node'
               }
           }
           steps {
               sh 'npm --version'
           }
       }
   }
}
