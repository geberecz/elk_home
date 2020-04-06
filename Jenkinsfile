pipeline {
	
	agent any

	stages {
	
		stage('Initialize') {
		
			steps {
				sh 'echo "I am running the job ${JOB_NAME} on host: $(hostname)"'
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