pipeline { 
  agent {
    docker {
      image 'node:7.8.0'
      args '-p 3000:3000 -p 3001:3001'  // Exponemos ambos puertos por si ejecutamos main o dev
    }
  }
  
  stages {
    stage('Build') {
      steps {
        sh 'npm install'
      }
    }

  }
}