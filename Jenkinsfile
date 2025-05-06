pipeline {
  agent {
    docker {
      image 'node:7.8.0'
      args '-p 3000:3000'
    }
  }

  environment {
    BRANCH = "${env.BRANCH_NAME}"
    HOST_PORT = "${env.BRANCH_NAME == 'main' ? '3000' : '3001'}"
    IMAGE_NAME = "${env.BRANCH_NAME == 'main' ? 'nodemain' : 'nodedev'}"
    TAG = 'v1.0.0'
  }

  stages {
    stage('Install') {
      steps {
        sh 'npm install'
      }
    }

    stage('Test') {
      steps {
        sh 'npm run test'
      }
    }

    stage('Build') {
      steps {
        sh 'npm run build'
      }
    }

    stage('Docker Build') {
      steps {
        sh 'docker build -t $IMAGE_NAME:$TAG .'
      }
    }

    stage('Deploy') {
      steps {
        sh 'echo "build deploy"'
      }
    }
  }
}
