pipeline {
  agent any

  tools {
    nodejs 'nodejs'
  }

  stages {
    stage('Delete old repo') {
      steps {
        sh 'rm -rf jenkins-test-project'
      }
    }

    stage('Clone repo') {
      steps {
        echo 'Cloning my repo'
        sh 'git clone https://github.com/JavaScriptForEverything/jenkins-test-project'
      }
    }

    stage('Install packages') {
      steps {
        dir('jenkins-test-project') {
          sh 'yarn install'
        }
      }
    }

    stage('Running App') {
      steps {
        dir('jenkins-test-project') {
          sh 'yarn start'
        }
      }
    }
  }
}
