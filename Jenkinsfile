pipeline {
  agent {
    docker {
      image 'maven:3-alpine'
      args '-v /root/.m2:/root/.m2'
    }
    
  }
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