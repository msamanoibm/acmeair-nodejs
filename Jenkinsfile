pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'hello'
      }
    }
    stage('Test') {
      steps {
        parallel(
          "Chrome": {
            echo 'testing in chrome'
            
          },
          "Firefox": {
            echo 'testing in firefox'
            
          }
        )
      }
    }
    stage('Deploy to DEV') {
      steps {
        echo 'deploying'
        sh '''echo "Deploying $BUILD_ID to DEV"
'''
      }
    }
    stage('Deploy to QA') {
      steps {
        sh 'echo "Deploying $BUILD_ID to QA"'
      }
    }
    stage('Deploy to PROD') {
      steps {
        sh 'echo "Deploying $BUILD_ID to prod"'
      }
    }
  }
}
