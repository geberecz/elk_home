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
			}
		}

		stage('Clean the workspace') {
			steps {
				echo 'I am cleaning the Workspace...'
				cleanWs()
			}
		}
	}

	post {
		always {
			echo "Always make last check..."
		}
		failure {
			echo "It ended with error..."
		}
		success {
			echo "It ended successfully..."
		}
	}
}