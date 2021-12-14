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

    stage('SonnarQube Scanner') {
      steps {
         withSonarQubeEnv('SonarQube') {
             sh 'mvn clean verify sonar:sonar -Dsonar.login=183183cc65dc440092a8e2b7b84a183c'
            }
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
