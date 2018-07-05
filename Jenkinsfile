pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'docker build -t app .'
      }
    }
    stage('Test') {
      steps {
        echo 'Test'
        sh '/bin/nc -vz localhost 22'
      }
    }
    stage('Push Registry') {
      steps {
        sh 'docker tag app:test app:stable'
        sh 'docker push pjlca/app:stable'
      }
    }
  }
}