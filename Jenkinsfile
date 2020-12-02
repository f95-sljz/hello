pipeline {
  agent {
    docker {
      image 'maven:3-alpine'
      args '-v /root/.m2:/root/.m2'
    }

  }
  stages {
    stage('build') {
      steps {
        sh 'echo "mvn build"'
      }
    }

    stage('test') {
      parallel {
        stage('test') {
          steps {
            sh 'echo "mvn test"'
          }
        }

        stage('test2') {
          steps {
            sh 'echo "test"'
          }
        }

      }
    }

    stage('deploy') {
      steps {
        sh 'echo "mvn package"'
      }
    }

  }
}