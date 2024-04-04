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
        sh '''git bisect start 198644632661c67b6c32f59e9047c11a70685e15 98ac319c0cff47b4d39a1a7b61b4e195cfa231e5
'''
        sh 'git bisect run mvn clean test'
      }
    }

  }
  tools {
    maven 'Maven 3.8.5'
    jdk 'Java 8'
  }
}