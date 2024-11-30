pipeline {
  agent any
  stages {
    stage('Echo Version') {
      steps {
        sh 'echo Print maven version'
        sh 'mvn -version'
      }
    }

    stage('Build') {
      steps {
        sh 'mvn clean package -Dskiptests=true'
        archiveArtifacts 'target/hello-demo-*.jar'
      }
    }

    stage('Unit Tests') {
      steps {
        sh 'mvn test'
        junit(testResults: 'target/surefire-reports/TEST-*.xml', keepProperties: true, keepTestNames: true)
      }
    }

  }
  tools {
    maven 'M399'
  }
}