pipeline{
  agent{
    node{
      label 'built-in' 
      customWorkspace '/home/att/project'
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
    stage('ansible-deploy'){
      steps{
        build 'ansible-deploy' 
      }
    }
  }
}
