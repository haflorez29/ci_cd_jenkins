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
        sh 'npm run test'
      }
    }

    stage('build docker image') {
      steps {
        sh 'echo "build docker imagen"'
      }
    }

    stage('deploy') {
      steps {
        sh 'echo "build deploy"'
      }
    }
  }
}