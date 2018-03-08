pipeline {
  agent any
  tools {
      maven 'mvn_3' 
  }
  
   stages {
      stage('Build') {
          steps {
              sh 'mvn -B -DskipTests clean package'
          }
      }
      stage('Test') {
          steps {
              sh 'mvn test'
          }
          post {
              always {
                  junit 'target/surefire-reports/*.xml'
              }
          }
      }
      stage('Deliver') {
          steps {
              echo 'Deploy To Server'
          }
      }
  }
}
