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
        echo 'echo...'
        retry(count: 3) {
          echo 'bonjour'
        }
      }
    }
  }
  environment {
    DISABLE_AUTH = 'true'
    DB_ENGINE = 'sqlite'
  }
}
