pipeline {
  agent any
  stages {
    stage('Build Backend') {
      parallel {
        stage('Build') {
          steps {
            echo 'Build Project'
          }
        }
        stage('Build UI') {
          steps {
            echo 'Build UI'
          }
        }
      }
    }
    stage('Test') {
      steps {
        echo 'Running Test'
      }
    }
    stage('Deploy') {
      steps {
        echo 'Deploy To Server'
      }
    }
  }
}