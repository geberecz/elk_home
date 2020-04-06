pipeline {
	
	options([parameters([string(defaultValue: 'latest', description: 'Input your parameter, e.g.: 1.0.3', name: 'VERSION', trim: false)])])

	agent any
	stages {
		stage('Initialize') {
			steps {
				sh 'echo "I am working on host: $(hostname)"'
			}
		}

		stage('Deploy') {
			steps {
				echo 'Initialized OK, I can deploy.'
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