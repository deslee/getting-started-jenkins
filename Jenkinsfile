pipeline {
  agent {
    label "master"
  }

  environment {
    AWS_ACCESS_KEY_ID = credentials('aws_id')
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
      publishLambda([awsRegion: 'us-east-1', functionARN: 'arn:aws:lambda:us-east-1:205556789738:function:gettingStartedJenkins', functionAlias: 'gettingStartedJenkins', useInstanceCredentials: true, versionDescription: ''])
			}
		}
  }

}
