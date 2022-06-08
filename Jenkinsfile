// this will start an executor on a Jenkins agent with the docker label
pipeline {
  agent any
  stages {
    stage('build base image') {
      steps {
        sh 'build-base'
      }
    }
    stage('run tests') {
      steps {
        sh 'build-test'
        sh 'test-unit'
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
