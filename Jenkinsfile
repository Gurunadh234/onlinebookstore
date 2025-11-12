pipeline {  
    agent {
        label "built-in"
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
        sh '''
          mvn verify sonar:sonar \
          -Dsonar.host.url=http://localhost:9000 \
          -Dsonar.projectKey=online-book-store \
          -Dsonar.projectName='online-book-store' \
          -Dsonar.token=sqa_9101c70f0104fcce48c67f19167f9e1cab2bab14
          '''
        }
      }
   }
}
