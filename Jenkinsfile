pipeline {
  agent {
    label "master"
  }

  environment {
    AWS_ACCESS_KEY_ID     = credentials('aws_id')
    AWS_SECRET_ACCESS_KEY = credentials('aws_secret')
    }

  tools {
    nodejs 'Node 6.10.3'
  }

	stages {
		stage('Build') {
			steps {
				sh 'npm install'
			}
		}

		stage('Test') {
			steps {
				sh 'echo No tests yet'
			}
		}

		stage('Deploy') {
			steps {
        sh 'export'

				deployLambda(
						[
  					  awsRegion: 'us-east-1',
  						description: '',
  						functionName: 'gettingStartedJenkins',
  						handler: 'index.handler',
  						memorySize: '128',
  						role: 'ARN arn:aws:iam::205556789738:role/lambda_basic_execution',
  						runtime: 'nodejs',
  						timeout: '10',
  						updateMode: 'full',
  						useInstanceCredentials: true
						]
				)
			}
		}
  }

}
