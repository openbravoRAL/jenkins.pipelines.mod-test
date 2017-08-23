pipeline {
  agent {
    node {
      label 'master'
    }
    
  }
  stages {
    stage('Dev') {
      steps {
        script {
          echo pwd()
          
          def repositoriesDir = 'repositories/' // move to environment
          
          dir(repositoriesDir) {
            // deleteDir(). Repo dir is never cleaned up because repos are cleaned
            def repoName = 'org.openbravo.base.axis2'
            def repo = 'https://code.openbravo.com/erp/mods/' + repoName
            cloneRepo(repo)
          }
        }
        
      }
    }
    stage('Setup') {
      steps {
        echo '${\'Setups\'+\'aa\'}'
        script {
          echo pwd()
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
    stage('puzzle up') {
      steps {
        script {
          sayHello('puzzle up')
        }
        
      }
    }
  }
}