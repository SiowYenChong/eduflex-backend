pipeline {
	environment{
		JAVA_TOOL_OPTIONS = "-Duser.home=/var/maven"
	}
    agent {
    	docker {
    		label "docker"
    		image "maven:3.6.0-jdk-13"
    		args "-v /tmp/maven:/var/maven/.m2 -e MAVEN_CONFIG=/var/maven/.m2"
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
