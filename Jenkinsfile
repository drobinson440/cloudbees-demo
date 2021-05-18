pipeline {
    agent {
      kubernetes {
        label "centos-7-pod-template"
      }
    }

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World!'
            }
        }
    }
}

