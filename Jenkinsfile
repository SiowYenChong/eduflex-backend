pipeline {
    agent {
     	label 'windows' 
    }
         stages {
            stage("Build") {
                steps {
                       sh "mvn -version"
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
