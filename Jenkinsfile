pipeline {
	agent any
	stages {
		stage('Initialize') {
			steps {
				echo 'Hello world!'
			}
		} 
		stage('Clean the workspace') {
			steps {
				echo 'I am cleaning zhe Workspace...'
				cleanWs()
			}
		}
	}
}