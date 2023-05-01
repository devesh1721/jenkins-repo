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
				sh "mvn clean install -DskipTests"
			}
		}
		stage('Test'){
			steps{
				sh "mvn test"
			}
		}
		stage('Deploy') {
			steps {
			    sh "mvn jar:jar deploy:deploy"
			}
		}
	}
}
