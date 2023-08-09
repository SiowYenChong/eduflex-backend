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
                       		sh 'docker build -t SiowYenChong/eduflex-backend .'
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
