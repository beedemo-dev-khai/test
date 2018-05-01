pipeline {
  agent {
    label 'jdk9'
  }
  stages {
    stage('Say Hello') {
      steps {
        echo 'Hello World!'
      }
    }
    stage('Java') {
      steps {
        sh 'java -version'
      }
    }
  }
}