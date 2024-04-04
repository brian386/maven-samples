pipeline {
  agent any
  stages {
    stage('check out') {
      steps {
        git(url: 'https://github.com/brian386/maven-samples.git', branch: 'master')
      }
    }

    stage('run') {
      steps {
        sh '''mvn clean
'''
        sh '''mvn test
'''
        sh '''mvn verify
'''
      }
    }

  }
  tools {
    maven 'Maven 3.8.5'
    jdk 'Java 8'
  }
}