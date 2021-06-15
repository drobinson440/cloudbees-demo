/*
pipeline {
    agent {
      kubernetes {
        label "centos-7-pod-template"
      }
    }

    stages {
        stage('Hello') {
            steps {
                echo 'Pod Template created in UI'
            }
        }
    }
}
*/

pipeline {
  agent {
    kubernetes {
      yaml """\
        apiVersion: v1
        kind: Pod
        metadata:
          labels:
            some-label: centos-7-template
        spec:
          containers:
          - name: centos7
            image: centos:7
            command:
            - cat
            tty: true
        """.stripIndent()
    }
  }
  stages {
    stage('Hello') {
      steps {
        container('centos7') {
          echo 'YAML within Jenkinsfile example.'
        }
      }
    }
  }
}

/*
pipeline {
  agent {
    kubernetes {
      defaultContainer 'centos7'
      yamlFile 'podTemplates/centos7.yaml'
    }
  }
  stages {
    stage('Hello') {
      steps {
        echo 'External YAML example.'
      }
    }
  }
}
*/
