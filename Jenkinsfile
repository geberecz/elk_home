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
				echo "Version a: ${params.VERSION}"
				echo "Version b: ${VERSION}"
				sh 'echo "I am running the job ${JOB_NAME} on host $(hostname)"'
				sh 'printenv | grep "PATH"'
			}
		}

		stage('Build for Develop') {
			when { branch "Development"}
			steps {
				echo "I am going to replace the file content on ${BRANCH_NAME} environment..."
				contentReplace( configs: [ 
					fileContentReplaceConfig( configs: [ 
						fileContentReplaceItemConfig( search: '(elasticsearch:)([0-9]+.[0-9]+.[0-9]+)|(latest)', replace: '$1${VERSION}', matchCount: 0) 
					],
					fileEncoding: 'UTF-8',
					filePath: 'elk_compose_stack.yml') 
				])
			}
		}


		stage('Deploy to Development') {
			when { branch "Development"}
			steps {
				echo "I am going to deploy the file to ${BRANCH_NAME} environment..."
				sshPublisher(
					publishers:
						[sshPublisherDesc(
							configName: 'elk1',
							transfers: [
								sshTransfer(
									execCommand: 'date >> /tmp/date.txt'
								)	
							])
						]
				)
			}
		}
	}

	post {
		always {
			echo "The overall result is: ${currentBuild.result}"
			echo 'I am always cleaning the Workspace...'
			echo '...but not now....'
			//cleanWs()

		}
		failure {
			echo "Build ended with error..."
		}
		success {
			echo "Build ended successfully..."
		}
	}
}