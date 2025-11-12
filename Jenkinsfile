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
          -Dsonar.token=sqp_797277937bae89b0ad4df253396859b7c1bc52d2
          '''
        }
      }
   }
}
