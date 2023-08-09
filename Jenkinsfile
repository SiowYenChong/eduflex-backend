pipeline {
	agent any
         stages {
            stage("Build") {
                steps {
                       sh "mvn clean install"
                }
            }
			stage('Build and Run Docker') {
	            steps {
	                script {
	                    // Pull a Docker image
	                    def dockerImage = docker.image('eduflex-backend:latest')
	                    dockerImage.pull()
	
	                    // Run a Docker container
	                    def dockerContainer = dockerImage.run()
	                    def containerId = dockerContainer.id
	
	                    // Execute a command inside the Docker container
	                    dockerContainer.inside {
	                        sh 'echo "Hello from Docker container!"'
	                    }
	
	                    // Stop and remove the container
	                    dockerContainer.stop()
	                    dockerContainer.remove()
	
	                    echo "Docker commands executed successfully."
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
