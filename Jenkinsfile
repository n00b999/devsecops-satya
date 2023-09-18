pipeline {
  agent any

  stages {
      stage('Build Artifact') {
            steps {
              sh "mvn clean package -DskipTests=true"
              archive 'target/*.jar' //so that they can be downloaded later-123test
            }
        }  
    stage('Docker Build and Push') {
      steps {
        sh 'printenv'
        sh 'docker build -t satyasrini111/numeric-app:""$GIT_COMMIT"" .'
        sh 'docker push satyasrini111/numeric-app:""$GIT_COMMIT""'
      }
    
     }
    }
}
