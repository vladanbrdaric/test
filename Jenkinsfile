pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh 'npm install'
      }
    }
    stage('unit-test') {
      when {
        anyOf {
          branch 'master'
          branch 'feature'
        }
      }
      steps {
        sh 'npm run unit-test'
      }
	}
    stage('integration-test') {
      when {
        anyOf {
          branch 'develop'
          branch 'master'
        }
      }
      steps {
        sh 'npm run integration-test'
      }
    }
  }
}
