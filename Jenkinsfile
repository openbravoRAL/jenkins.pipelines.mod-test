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
          sayHello()
        }
        
      }
    }
    stage('Clone repositories') {
      steps {
        parallel(
          "01 ERP": {
            script {
              sayHello()
            }
            
            
          },
          "10 Retail.pack": {
            script {
              sayHello()
            }
            
            
          }
        )
      }
    }
  }
}