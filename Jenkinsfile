pipeline {
  agent none

  environment {
    DOCKER_IMAGE = 'samcli/react-jenkins'
    DOCKER_TAG = 'latest'
  }

  stages {
    stage('Checkout') {
      agent any
      steps {
        git branch: 'main', url: 'https://gitlab.com/groupkiber/jenkins-react.git'
      }
    }

    stage('Build & Test') {
      agent {
        docker { image 'node:18'; args '-u root' }
      }
      steps {
        sh 'npm ci'
        sh 'npm run test'
        sh 'npm run coverage'
        sh 'npm run build'
      }
      post {
        always {
          archiveArtifacts artifacts: 'coverage/**', fingerprint: true
        }
      }
    }

    stage('Build Docker Image') {
      agent any
      steps {
        sh 'docker build -t $DOCKER_IMAGE:$DOCKER_TAG .'
      }
    }

    stage('Push a Docker Hub') {
      agent any
      steps {
        withCredentials([usernamePassword(credentialsId: 'docker-hub-credes-token', usernameVariable: 'DOCKER_USER', passwordVariable: 'DOCKER_PASS')]) {
          sh '''
            echo "$DOCKER_PASS" | docker login -u "$DOCKER_USER" --password-stdin
            docker push $DOCKER_IMAGE:$DOCKER_TAG
          '''
        }
      }
    }
  }
}
