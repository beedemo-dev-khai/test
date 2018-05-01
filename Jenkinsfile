pipeline {
  agent {
    label 'jdk8'
  }
  stages {
    stage('Say Hello') {
      steps {
        echo "Hello ${MY_NAME}!"
        echo "${TEST-USER_USR}"
        echo "${TEST_USER_PSW}"
      }
    }
    stage('Java') {
      steps {
        sh 'java -version'
      }
    }
  }
  environment {
    MY_NAME = 'Khai'
    TEST_USER = credentials('test-user')
  }
}