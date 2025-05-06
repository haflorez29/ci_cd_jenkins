pipeline {
  agent {
    docker {
      image 'node:7.8.0'
      args '-p 3000:3000'
    }

  }

  environment {
    BRANCH = "${env.BRANCH_NAME}"
    HOST_PORT = "${env.BRANCH_NAME == 'main'? '3000' : '3001'}"
    IMAGE_NAME = "${env.BRANCH_NAME == 'main' ? 'nodemain' : 'nodedev}"
    TAG = 'v1.0.0'
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

    stage('build') {
      steps {
        sh 'npm run build'
      }
    }

    stage('build docker image') {
      steps {
        sh 'docker build -t $IMAGE_NAME:$TAG'
      }
    }

    stage('deploy') {
      steps {
        sh 'echo "build deploy"'
      }
    }
  }
}