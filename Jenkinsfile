pipeline {
  agent any

  tools {
    jdk 'jdk-11'
    maven 'mvn-3.6.3'
  }

  stages {
    stage('Get Code') {
      steps {
        git 'https://github.com/kietpham0703/milestone.git'
        sh 'ls'
      }
    }
    stage('BUILD') {
      steps {
       withMaven(maven : 'mvn-3.6.3') {
            sh "mvn install"
        }
      }
    }

  }
}
