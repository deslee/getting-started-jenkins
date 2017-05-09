pipeline {
    agent {
	label "master"
    }

    tools {
        nodejs 'Node 6.10.3'
    }

    stages {
        stage('example - echo') {
            steps {
                sh 'echo hi 2'
                sh 'mkdir test'
                sh 'ls'
                sh 'pwd'
            }
        }

        stage('example - npm') {
            steps {
                sh 'npm --version'
            }
        }
    }
}
