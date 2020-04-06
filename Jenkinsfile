pipeline {
	agent any
	stages {
		stage('Initialize') {
			steps {
				parameters {
  					string defaultValue: 'latest', description: 'Input your parameter (e.g.: 1.0.3)', name: 'VERSION', trim: false
				}
			}
		} 
		stage('Clean the workspace') {
			steps {
				echo 'Your version is params.VERSION'
				echo 'I am cleaning the Workspace...'
				cleanWs()
			}
		}
	}
}