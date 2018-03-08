pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'mvn -B -DskipTests clean package'
        archiveArtifacts(artifacts: 'target/**/*.jar', fingerprint: true, onlyIfSuccessful: true)
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
  tools {
    maven 'mvn_3'
  }
}