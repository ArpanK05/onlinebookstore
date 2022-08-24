pipeline{
  agent{
   node {
      label 'built-in'
      customWorkspace '/root/repo'
    }
  }
  stages{
    stage('Build-Code'){
      steps{
        sh 'mvn clean package'
        sh 'aws s3 cp ./target/*.war s3://apran-deploy/master/'
        }
      }
    }
  }


