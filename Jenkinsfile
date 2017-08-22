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
          
          def repo = 'ssh://hg@bitbucket.org/RafaOpenbravo/jenkins.pipelines.sharedlibrary'
          checkout changelog: false, poll: false, scm: [$class: 'MercurialSCM', source: repo, clean: false, credentialsId: '', revision: "default", revisionType: "BRANCH"]
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