pipeline {
	
	agent any

	parameters {
		string(defaultValue: 'latest', description: 'Input your parameter, e.g. 1.0.3', name: 'VERSION', trim: false)
	}

	environment {
		H = """${sh(
			returnStdout: true,
			script: 'echo "$(hostname)"'
        )}"""

	}

	stages {
	
		stage('Initialize') {
		
			environment {
				LOCAL_PATH='/home/ec2-user'
			}
			steps {
				echo "Version: ${params.VERSION}"
				echo "Hostname: ${H}"
				sh 'echo "I am running the job ${JOB_NAME} on host $(hostname)"'
				sh 'printenv | grep "PATH"'
			}
		}

		stage('Deploy') {
			steps {
				echo 'Initialized OK, I can deploy.'
				}
			}
		}

		stage('Clean the workspace') {
			steps {
				echo 'I am cleaning the Workspace...'
				cleanWs()
			}
		}
	}