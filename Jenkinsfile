pipeline {
  agent any

  tools {
    nodejs "SIT753_Task8_1C" // Matches your configured NodeJS name
  }

  stages {
    stage('Checkout') {
      steps {
        git branch: 'main', url: 'https://github.com/TKaushik98/8.2CDevSecOps.git'
      }
    }

    stage('Install Dependencies') {
      steps {
        sh 'npm install'
      }
    }

    stage('Run Tests') {
      steps {
        sh 'npm test || true'
      }
    }

    stage('Generate Coverage Report') {
      steps {
        sh 'npm run coverage || true'
      }
    }

    stage('NPM Audit (Security Scan)') {
      steps {
        sh 'npm audit || true'
      }
    }
  }
}
