pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'printenv'
      }
    }
    stage('Quality Scan') {
      steps {
        echo 'sonar'
      }
    }
    stage('Package & Publish') {
      steps {
        echo 'pp'
      }
    }
    stage('Deploy to QA') {
      steps {
        parallel(
          "Automated Tests": {
            echo 'qa'
            
          },
          "Performance Tests": {
            echo 'perf'
            
          },
          "Security Tests": {
            echo 'security'
            
          }
        )
      }
    }
    stage('Deploy to UAT') {
      steps {
        echo 'tm'
      }
    }
    stage('Deploy to Preprod') {
      steps {
        echo 'preprod'
      }
    }
    stage('Deploy to production') {
      steps {
        echo 'prod'
      }
    }
  }
  environment {
    DISABLE_AUTH = 'true'
    DB_ENGINE = 'sqlite'
  }
}