pipeline {
  agent {
    label 'default'
  }
  stages {
    stage('Say Hello') {
      steps {
        echo "Hello ${MY_NAME}!"
        echo "This is my ${params.Name}!"
        echo "${TEST_USER_USR}"
        echo "${TEST_USER_PSW}"
      }
    }
    stage('Checkpoint') {
       agent none
       steps {
          checkpoint 'Checkpoint'
       }
    }
    stage('Testing') {
      failFast true
      parallel {
        stage('Java 8') {
          agent { label 'jdk8' }
          steps {
            sh 'java -version'
            sleep time: 10, unit: 'SECONDS'
          }
        }
        stage('Java 9') {
          agent { label 'jdk9' }
          steps {
            sh 'java -version'
            sleep time: 20, unit: 'SECONDS'
          }
        }
      }
    }
  }
  environment {
    MY_NAME = 'Khai'
    TEST_USER = credentials('test-user')
  }
  post {
    aborted {
      echo 'Why didn\'t you push my button?'
      
    }
    
  }
  parameters {
    string(name: 'Name', defaultValue: 'whoever you are', description: 'Who should I say hi to?')
  }
}
