pipeline {
    agent any
    parameters {
        string(name: 'Greeting', defaultValue: 'Hello', description: 'How should I greet the world?')
    }

	stages {
	
		stage('Initialize') {
		
			environment {
				LOCAL_PATH='/home/ec2-user'
			}
			steps {
				echo "Version: ${params.Greeting}"
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