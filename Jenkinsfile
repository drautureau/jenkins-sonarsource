pipeline {
  agent any
  stages {
    stage('Build') {
      agent any
      steps {
        echo 'Building ...'
      }
    }
    stage('ITs') {
      parallel {
        stage('IT 1') {
          agent any
          steps {
            echo 'Running IT 1 ...'
          }
        }
        stage('IT 2') {
          agent any
          steps {
            echo 'Running IT 2 ...'
          }
        }
      }
    }
    stage('Promote') {
      steps {
        echo 'Promoting ...'
      }
    }
    stage('Release') {
      agent any
      steps {
        input 'LGTM?'
      }
    }
  }
}