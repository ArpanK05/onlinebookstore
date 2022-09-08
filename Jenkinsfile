pipeline{
  agent{
    node{
      label 'built-in' 
      customWorkspace '/root/project'
    }
  }
  tools{
   maven 'maven-3.8.6' 
  }
  stages{
    stage('build-app'){
      steps{
        sh 'mvn clean install'
      }
    }
  }
}
