pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        echo 'compiling sysfoo app'
        sh 'mvn compile'
      }
    }

    stage('test') {
      steps {
        echo 'unit testing sysfoo app'
        sh 'mvn clean test'
      }
    }

    stage('package') {
      steps {
        echo 'package sysfoo app'
        sh 'mvn package -DskipTests'
        archiveArtifacts 'target/*.war'
      }
    }

  }
  tools {
    maven 'Maven 3.6.3'
  }
}