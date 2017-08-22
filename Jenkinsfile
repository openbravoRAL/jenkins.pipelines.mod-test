

pipeline {
  agent {
    node {
      label 'master'
    }
    
  }
  stages {
    stage("Setup \u273F") {
      steps {
        println env.BUILD_NUMBER

        // deleteDir() // clean the part of the workspace that is not the repositories

        echo "Workspace ${WORKSPACE}! Context: ${CONTEXT}"
        sh 'echo ${WORKSPACE}'

      }
    }
    stage("Run shared script \u2623") {
      steps {
        script {
            def helloworld = new sharedlibrary.HelloWorld()
            println helloworld.say()
        }
      }
    }
  }
  environment {
    WORKSPACE = pwd()
    CONTEXT = 'context'
    MODULES = 'modules'
    REPO_ERP = 'https://code.openbravo.com/erp/devel/pi'
    REPO_MODULES = 'https://code.openbravo.com/erp/mods/org.openbravo.util.db'
  }
}