pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Running Build fase'
      }
    }

    stage('Test') {
      steps {
        echo 'Running Test'
        sleep 5
        build 'unicorn-test'
      }
    }

  }
}