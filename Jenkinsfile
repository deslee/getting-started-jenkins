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
        sh 'echo id is $AWS_ACCESS_KEY_ID'
			}
		}

		stage('Deploy') {
			steps {
        sh 'export'

				deployLambda(
						[
              useInstanceCredentials: true,
  					  awsRegion: 'us-east-1',
  						description: '',
              artifactLocation: './',
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
