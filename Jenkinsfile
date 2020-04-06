pipeline {
	
	agent any

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
				echo "Hostname: ${H}"
				sh 'echo "I am running the job ${JOB_NAME} on host $(hostname)"'
				sh 'printenv | grep "PATH"'
			}
		}

		stage('Deploy') {
			steps {
				echo 'Initialized OK, I can deploy.'
				withCredentials([usernamePassword(credentialsId: '7dc1a043-ad75-40d6-8f30-ebc0cc80b3eb',\
				 passwordVariable: 'PASSWD',\
				 usernameVariable: 'USER')]) {
    				echo "My username and pasword is: $USER $PASSWD"
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
}