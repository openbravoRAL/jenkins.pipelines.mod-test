pipeline {
  agent {
    node {
      label 'master'
    }
    
  }
  stages {
    stage('Setup') {
      steps {
        echo 'Setup'
        script {
          sayHello('Setup')
        }
        
      }
    }
    stage('Clone repositories') {
      steps {
        parallel(
          "01 erp": {
            script {
              sayHello('erp')
            }
            
            
          },
          "10 retail.pack": {
            script {
              sayHello('retail.pack')
            }
            
            
          }
        )
      }
    }
    stage('error') {
      steps {
        script {
          sayHello('puzzle up')
        }
        
      }
    }
  }
}