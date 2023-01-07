// this will start an executor on a Jenkins agent with the docker label
pipeline {
  agent any
  stages {
    stage('build base image') {
      steps {
        echo 'building...'
        sh 'make build-base'
      }
    }
    stage('run tests') {
      steps {
        echo 'testing..'
        sh 'make build-test'
        sh 'make test-unit'
        sh 'ls'
        junit 'report/report.xml'
      }
    }
    stage('build image') {
      steps {
        sh 'make build'
      }
    }
  }
}
