pipeline {
	
	agent any

	stages {
	
		stage('Initialize') {
		
			steps {
				sh 'echo "I am working on host: $(hostname)"'
				echo "I am running the job: ${JOB_NAME}"
				echo 'I am running the job: ${JOB_NAME}'
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