pipeline {
  agent any
  tools {
      maven 'mvn_3' 
  }
  stages {
    stage('Build') {
      parallel {
        stage('Build Backend') {
          agent {
            node {
              label 'java'
            }
            
          }
          steps {
            sh 'mvn --version'
            echo 'Build Project'
            sleep 30
          }
        }
        stage('Build UI') {
          agent {
            node {
              label 'node'
            }
            
          }
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
