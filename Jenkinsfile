pipeline {
  agent {
    docker {
      image 'node:6-alpine'
      args '-p 3000:3000  -e "npm_config_proxy=http://www-proxy-hqdc.us.oracle.com:80"'
    }

  }
  stages {
    stage('Build') {
      steps {
        sh 'npm install'
      }
    }
    stage('Test') {
      environment {
        CI = 'true'
      }
      steps {
        sh './jenkins/scripts/test.sh'
      }
    }
  }
}