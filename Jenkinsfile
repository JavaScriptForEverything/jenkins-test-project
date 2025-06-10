pipeline {
	agent any

	tools {
		// Make sure this matches the name you configured in Jenkins Global Tools
		nodejs 'NodeJS 24.1.0'
	}

	stages {

		stage('clone git repo') {
			steps {
				echo 'cloning start via jenkins'
				sh 'ls -l'
			}
		}

		stage('build app') {
			steps {
				sh 'yarn install'
				sh 'yarn build'
			}
		}
		stage('run app') {
			steps {
				sh 'yarn start'
			}
		}
	}
}
