pipeline {
  agent {
    docker {
      image 'node:7.8.0'
      args '-p 3000:3000'
    }

  }
  stages {
    stage('build') {
      steps {
        sh 'npm install'
      }
    }

    stage('test') {
      steps {
        sh './jenkins/scripts/test.sh'
      }
    }

  }
}