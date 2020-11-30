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
        deploy adapters: [tomcat7(credentialsId: '40aa2f7f-ac43-4d11-95a9-30964c40f24b', path: '', url: 'http://localhost:8081')], contextPath: 'JenkinsJSF', war: '**/*.war'  
      }
    }    
  }
}
