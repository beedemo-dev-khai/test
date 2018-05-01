pipeline {
  agent any
  stages {
    stage('Say Hello') {
      steps {
        echo 'Hello World!'
      }
    }
    stage('error') {
      steps {
        sh 'java -version'
      }
    }
  }
}