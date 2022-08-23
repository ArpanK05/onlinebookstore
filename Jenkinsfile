pipeline { 
  agent {
    label 'built-in'
  }
  stages { 
    stage('build-code') { 
      steps { 
        sh 'mvn clean package' 
        sh 'aws s3 cp ./target/onlinebookstore*.war s3://arpan-deploy/Container/'
        } 
      }
     stage('deployOnQA'){
       steps{
          build job: "DeployQA"
       } 
    }
  }
}

