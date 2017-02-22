pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'printenv'
      }
    }
    stage('Echo') {
      steps {
        parallel(
          "Echo": {
            retry(count: 3) {
              echo 'bonjour'
            }
          },
          "Echo 2": {
            sleep '1'
          },
          "Echo 3": {
            retry(count: 3) {
              echo 'echo 3'
            }
          }
        )
      }
    }
    stage('Tear down') {
      steps {
        echo 'done'
      }
    }
  }
  environment {
    DISABLE_AUTH = 'true'
    DB_ENGINE = 'sqlite'
  }
}
