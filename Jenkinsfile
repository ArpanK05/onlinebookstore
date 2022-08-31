pipeline{
	agent{
		label 'iamops'
		customWorkspace '/root/project/'
	}

	stages{
		stage('build-deploy-app'){
			steps{
				sh 'mvn clean install'
				sh 'cp ./onlinebookstore/target/*.war /root/apache-tomcat-9.0.65/webapps/'
				sh 'cd /root/apache-tomcat-9.0.65/bin && ./startup.sh'

			}
		}
	}
}
