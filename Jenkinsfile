pipeline {
	agent any
	stages {
		stage('Initialize') {
			steps {
				sh 'hostname'
			}
		} 
		stage('Clean the workspace') {
			steps {
				echo 'I am cleaning the Workspace...'
				cleanWs()
			}
		}
	}
}