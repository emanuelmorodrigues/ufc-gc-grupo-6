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
        sleep 30
        build(job: 'unicorn-test', propagate: true)
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
            mail(subject: '[Jenkins] Email Check - Prática', body: 'O Teste rodou com sucesso', from: 'manel_mr@alu.ufc.br', to: 'jeferson@alu.ufc.br', cc: 'thiagotharles@alu.ufc.br, monicayasmin@alu.ufc.br')
          }
        }

      }
    }

  }
}