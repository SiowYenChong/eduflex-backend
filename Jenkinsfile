pipeline {
	environment{
		JAVA_TOOL_OPTIONS = "-Duser.home=/var/maven"
	}
    agent { dockerfile true }
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
