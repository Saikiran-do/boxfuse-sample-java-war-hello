pipeline {

  agent any
  environment {
      PATH = "/bin/mvn:$PATH"
  }


  stages {
      stage("Get the code from GITGIUB")
{
          steps
{
            git branch: 'master', url: 'https://github.com/Saikiran-do/boxfuse-sample-java-war-hello.git'
          
          }
      }




      stage("build code"){
          steps{
              sh "mvn clean package"
          }
      }
      stage("deploy the code"){
          steps{
             deploy adapters: [tomcat9(credentialsId: 'apache', path: '', url: 'http://54.145.217.250:8080')], contextPath: 'Pipe', war: '**/*.war'
          }
      }
  }
}
