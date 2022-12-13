pipeline {
  agent any {
    environment {
      Path = "C:\apache-maven-3.8.6\bin:$Path"
    }
    stages {
      stage('SCM_chekcout') {
        steps {
          git "https://github.com/mannepallyvinod/Sample_Webapp.git"
        }
      }
      stage('Build') {
        steps {
          bat "mvn install"
        }
      }
      stage('Copy' {
        steps {
          bat "copy target\\Sample_Webapp.war\\D:\\apache-tomcat-9.0.65\\webapps"
        }
      }
      stage('Deploy') {
        steps {
          bat "deploy adapters: [tomcat9(credentialsId: '5995532a-4115-4c29-83ae-14d4ec7fc58a', path: '', url: '')], contextPath: 'D:\\apache-tomcat-9.0.65\\webapps', war: 'Sample_Webapp'"
        }
      }
    }
  }
}
