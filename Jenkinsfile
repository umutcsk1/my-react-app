pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        // GitHub repository'sinden kodun çekilmesi
        git 'https://github.com/umutcsk1/my-react-app'
      }
    }
    stage('Build Docker Image') {
      steps {
        script {
          // Docker imajının oluşturulması
          docker.build('react-app:latest')
        }
      }
    }
    stage('Run Docker Container') {
      steps {
        script {
          // Docker container'ın çalıştırılması
          docker.image('react-app:latest').run('-p 3000:3000')
        }
      }
    }
  }
}
