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
        build(job: 'unicorn-test', propagate: true)
      }
    }

    stage('Done') {
      steps {
        echo 'Test Completed'
      }
    }

  }
}