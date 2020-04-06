pipeline {
	agent any
	stages {
		stage('Initialize') {
			steps {
				sh 'echo "I am working on host: $(hostname)"'
			}
		}

		stage('Deploy') {
			when {
				expression {
					currentBuid.result == null || currentBuid.result == 'SUCCESS'
				}
			}
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