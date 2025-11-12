pipeline {  
    agent {
      label 'dev'
    }
    stages {
      stage('Build') {
        steps {
          sh 'mvn clean package'
        }
      }
      stage('Test') {
        steps {
            sh 'mvn clean test'
        }
      }
      stage('SonarQube') {
        steps {
          sh 'echo Sonar'
        }
      }
   }
}
