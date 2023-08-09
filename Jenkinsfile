pipeline {
	environment {
		JAVA_TOOL_OPTIONS = "-Duser.home=/home/jenkins"
	}
	agent {
		dockerfile {
			label "docker"
			environment {
				MAVEN_CONFIG = "/home/jenkins/.m2"
			}
			args "-v /tmp/maven:/home/jenkins/.m2"
		}
	}
	stages {
		stage("Build") {
			steps {
				sh "mvn clean install"
			}
		}
	}
	post {
		always {
			cleanWs()
		}
	}
}
