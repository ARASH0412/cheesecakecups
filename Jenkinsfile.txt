pipeline {
  agent any

  stages {
    stage('Hello') {
      steps {
        echo "Hello from Jenkins pipeline!"
      }
    }
    stage('Simple Shell') {
      steps {
        bat 'echo building... & ver'
      }
    }
  }

  post {
    always { echo "Finished build ${env.JOB_NAME} #${env.BUILD_NUMBER}" }
  }
}
