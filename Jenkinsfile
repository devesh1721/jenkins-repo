pipeline {
	agent any
	tools {
		maven "MAVEN_HOME"
	}
	stages {
		stage('Build Maven project'){
			steps {
				git "https://github.com/devesh1721/jenkins-assignment.git"
				sh "mvn clean install -DskipTests"
			}
		}
		stage('Create docker image'){
			steps{
				script{
					sh "docker build -t  devesh29476/bookservicev9 ."
				}
			}
		}
		stage('Pushing dcoker image to docker hub '){
			steps{
				script{
					withCredentials([string(credentialsId: 'docker-pwd', variable: 'dockerpwd')]) {
					}
					sh "docker login --username  devesh29476 --password-stdin {dockerpwd} ."
					sh "docker push devesh29476/bookservicev9"
				}
			}
		}
		stage('Test'){
			steps{
				sh "mvn test"
			}
		}
	}
}
