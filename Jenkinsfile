pipeline {
  agent any

  tools {
    jdk 'openjdk-11.0.1_linux-x64_bin'
    maven 'mvn-3.6.3'
    env.JAVA_HOME = "${jdk}"
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
