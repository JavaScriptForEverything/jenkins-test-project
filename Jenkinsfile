pipeline {
	agent any

	tools {
		// Make sure this matches the name you configured in Jenkins Global Tools
		nodejs 'NodeJS 24.1.0'
	}

	stages {

		stage('clone git repo') {
			steps {
				echo 'cloning start ...'
				sh 'rm -rf *'
				sh 'git clone https://github.com/JavaScriptForEverything/jenkins-test-project'
				sh 'ls -l'
				echo 'cloning end'
			}
		}

		stage('build app') {
			steps {
				dir('jenkins-test-project') {  // Use `dir` instead of `cd`
					sh 'yarn install'
					sh 'yarn build'
				}
			}
		}
		stage('run app') {
			steps {
				dir('jenkins-test-project') {
						sh 'yarn start'
				}
			}
		}
	}
}
