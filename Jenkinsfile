pipeline {
  agent any
  stages {
    stage('compilar') {
      steps {
        withMaven(maven: 'Maven-1') {
          bat 'mvn clean install -DskipTests=true'
        }
      }
    }
    stage('desplegar') {
      steps {
        deploy adapters: [tomcat7(credentialsId: '7a580f23-3bb3-4f8a-89f7-c896e4259bc5', path: '', url: 'http://localhost:8081')], contextPath: 'JenkinsNormal', war: '**/*.war'
      }
    }    
  }
}
