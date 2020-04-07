pipeline {
    
    agent any
    
    parameters {
        string(name: 'VERSION', defaultValue: 'latest', description: 'Input your parameter, e.g. 1.0.3', trim: false)
    }

	stages {
	
		stage('Initialize') {
		
			environment {
				LOCAL_PATH='/home/ec2-user'
			}
			steps {
				echo "Version: ${params.VERSION}"
				sh 'echo "I am running the job ${JOB_NAME} on host $(hostname)"'
				sh 'printenv | grep "PATH"'
			}
		}

		stage('Deploy') {
			steps {
				echo 'Initialized OK, I can deploy.'
				sh 'ls Junk'
			}
		}
	}

	post {
		always {
			echo 'I am always cleaning the Workspace...'
			cleanWs()
			echo "The result is: currentBuild.result"
		}
		failure {
			echo "It ended with error..."
		}
		success {
			echo "It ended successfully..."
		}
	}
}