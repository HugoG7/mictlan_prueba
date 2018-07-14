pipeline {
  agent any
  stages {
    stage('Install') {
      steps {
        sh 'npm install'
        emailext(subject: 'Installed Success', body: 'The current installation was correct, continuing with process...', attachLog: true, to: 'hugo')
      }
    }
    stage('Build') {
      steps {
        sh 'npm run build'
      }
    }
    stage('Test') {
      steps {
        sh 'npm run test'
        emailext(subject: 'Tested Finished', body: 'Tests were finished', attachLog: true, to: 'messi')
      }
    }
  }
}