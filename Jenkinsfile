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

    stage('Done') {
      parallel {
        stage('Done') {
          steps {
            echo 'Test Completed'
          }
        }

        stage('Email check') {
          steps {
            mail(subject: '[Jenkins] Test Passed', body: 'O Script de test rodou com sucesso', from: 'manel_mr@alu.ufc.br', to: 'jeferson@alu.ufc.br', cc: 'thiagotharles@alu.ufc.br, monicayasmin@alu.ufc.br')
          }
        }

      }
    }

  }
}