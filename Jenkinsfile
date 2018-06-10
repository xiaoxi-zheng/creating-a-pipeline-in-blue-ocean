pipeline {
  agent {
    docker {
      image 'node:6-alpine'
      args '-p 3000:3000 -e "PROXY_HOST=www-proxy-hqdc.us.oracle.com" -e "PROXY_PORT=80"'
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