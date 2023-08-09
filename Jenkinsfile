pipeline {
	agent any
         stages {
            stage("Build") {
                steps {
                       sh "mvn clean install"
                }
            }
            stage("Build docker image") {
                steps {
                       script{
                       		sh 'docker build -t siowyenchong/eduflex-backend .'
                       }
                }
            }
         }
		post{
			always{
				cleanWs()
			}
		}
}
