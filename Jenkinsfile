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
      agent {
        label 'QA'
        }
       steps{
        dir('/root/wars'){
          sh 'aws s3 cp s3://arpan-deploy/Container/ . --recursive'
           sh 'docker-compose up -d --scale tomcat=2'
        }
      } 
    }
  }
}
