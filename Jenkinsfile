pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build Backend') {
          steps {
            echo 'Build Project'
            sleep 30
          }
        }
        stage('Build UI') {
          steps {
            echo 'Build UI'
            sleep 30
          }
        }
      }
    }
    stage('Test') {
      parallel {
        stage('Test Backend') {
          steps {
            echo 'Running Test'
          }
        }
        stage('Test UI') {
          steps {
            sleep 30
          }
        }
        stage('Test Both') {
          steps {
            sleep 45
          }
        }
      }
    }
    stage('Deploy') {
      steps {
        echo 'Deploy To Server'
      }
    }
  }
}