pipeline {
  agent {
    node {
      label 'master'
    }
    
  }
  stages {
    stage('Setup') {
      steps {
        echo 'empty'
        library 'SharedLibrary'
        script {
          echo sayHello
        }
        
      }
    }
  }
}