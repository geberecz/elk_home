pipeline {
	
	agent any

	environment {
		GLOBAL_PATH='/home'
	}

	stages {
	
		stage('Initialize') {
		
			environment {
				LOCAL_PATH='/home/ec2-user'
			}
			steps {
				sh 'echo "I am running the job ${JOB_NAME} on host $(hostname)"'
				sh 'printenv'
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