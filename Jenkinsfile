pipeline {
	agent any
	tools {
		maven "apache-maven-3.6.3"
	}
	stages {
		stage('Build'){
			steps {
				git "https://github.com/devesh1721/jenkins-assignment.git"
				bat "mvn clean install -DskipTests"
			}
		}
		stage('Test'){
			steps{
				bat "mvn test"
			}
		}
		stage('Deploy') {
			steps {
			    bat "mvn jar:jar deploy:deploy"
			}
		}
	}
}
