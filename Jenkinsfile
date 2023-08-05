pipeline {
    agent any
    stages {
        stage("Build") {
            steps {
                sh "mvn -version"
                withMaven(maven: 'apache-maven-3.9.2') {
                    bat 'mvn clean compile'
                }
            }
        }
    }
    post {
        always {
            cleanWs()
        }
    }
}