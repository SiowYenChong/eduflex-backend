pipeline {
    agent any
    tools{
    	maven "3.6.0"
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
