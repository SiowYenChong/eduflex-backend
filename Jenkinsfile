pipeline {
    agent any
    tools{
        maven 'maven_3_5_0'
    }
    stages{
        stage('Build Maven'){
            steps{
                checkout scmGit(branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'file:///C:/Users/Clarr/git/eduflex-backend']])
                sh 'mvn clean install'
            }
        }
        stage('Build docker image'){
            steps{
                script{
                    sh 'docker build -t siowyenchong/eduflex-backend .'
                }
            }
        }
        stage('Push image to Hub'){
            steps{
                script{
	                withCredentials([string(credentialsId: 'dockerhub-pwd', variable: 'dockerhubpwd')]) {
					    sh 'docker login -u siowyenchong -p ${dockerhubpwd}'
					}
                   sh 'docker push siowyenchong/eduflex-backend'
                }
            }
        }
    }
}