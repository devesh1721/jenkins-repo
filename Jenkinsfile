pipeline {
	agent any
	environment {
		mavenHome = tool 'apache-maven-3.6.3'
	}
	tools {
		jdk 'jdk-17.0.2'
	}
	stages {
		stage('Build'){
			steps {
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
