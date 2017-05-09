pipeline {
  agent {
    label "master"
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
      publishLambda([awsAccessKeyId: 'AKIAIRYYRDKI67MKOROA', awsRegion: 'us-east-1', awsSecretKey: '{AQAAABAAAAAwTjOx8CvsXVW2uNpy5drxnQ+c3OsfMtK3yg23FBnXjmXZFOIUAnZ/5Rgt/IsJFmRSRXJekCHJX3DeiPohyU/+dQ==}', functionARN: 'arn:aws:lambda:us-east-1:205556789738:function:gettingStartedJenkins', functionAlias: '', useInstanceCredentials: false, versionDescription: ''])
			}
		}
  }

}
