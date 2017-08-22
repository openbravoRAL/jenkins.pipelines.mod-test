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
          def hello = new sharedlibrary.HelloWorld()
          println hello.say()
        }
        
      }
    }
  }
}