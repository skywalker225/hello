pipeline {
  agent none
  stages {
    stage('Build') {
      agent { dockerfile true }
      steps {
        echo 'Building...'
        sh 'node --version'
        sh 'svn --version'
      }
    }
    stage('Test') {
      steps {
        echo 'Testing...'
      }
    }
    stage('Deploy') {
      steps {
        echo 'Deploying...'
      }
    }
  }
}
