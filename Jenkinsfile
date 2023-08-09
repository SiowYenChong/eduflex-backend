pipeline {
	agent {
    	docker {
    		label 'docker'
    		image "maven:3.6.0-jdk-13"
		}
    }
         stages {
            stage("Build") {
                steps {
                       sh "mvn clean install"
                }
            }
         }
		post{
			always{
				cleanWs()
			}
		}
}
