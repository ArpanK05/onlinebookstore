pipeline{
  agent{
    node{
      label 'built-in' 
      customWorkspace '/root/project'
    }
  }
  stages{
    stage('build-app'){
      steps{
        sh 'mvn clean install'
        sh 'cp ./target/*.war /root/server/apache-tomcat-9.0.65/webapps/'
        sh 'cd /root/server/apache-tomcat-9.0.65/bin && ./startup.sh'
      }
    }
  }
}
