pipeline {
  agent any
  stages {
    stage('Clone Repository') {
      steps {
        git 'https://github.com/<bgonikai2>/<your-repo>.git'
      }
    }
    stage('Build Docker Image') {
      steps {
        script {
          dockerImage = docker.build("myapp:${env.BUILD_ID}")
        }
      }
    }
    stage('Run Docker Container') {
      steps {
        script {
          dockerImage.run('-p 3000:3000')
        }
      }
    }
  }
}

