pipeline {
	agent any
	tools {
		maven "MAVEN_HOME"
	}
	stages {
		stage('Build'){
			steps {
				git "https://github.com/devesh1721/jenkins-assignment.git"
				sh "mvn clean install -DskipTests"
			}
		}
		stage('Test'){
			steps{
				sh "mvn test"
			}
		}
	}
}
