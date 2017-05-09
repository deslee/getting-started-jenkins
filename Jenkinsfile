pipeline {
    agent {
	label "master"
    }

    tools {
        nodejs 'Node 6.x'
    }

    stages {
        stage('example - echo') {
            steps {
                sh 'echo hi'
            }
        }

        stage('example - npm') {
            steps {
                sh 'npm --version'
            }
        }
    }
}
