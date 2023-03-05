pipeline {
  agent any
  environment {
    PATH = "/opt/apache-maven-3.9.0/bin:${PATH}"
  }
  stages {
    stage("git clone code") {
      steps{
        git 'https://github.com/architectdevops7/jenkins-cicd.git'
      }
    }
    
    stage("maven build code"){
      steps{
        sh 'mvn clean package'
      }
    }
    stage("maven test code"){
      steps{
        sh 'mvn test'
      }
    }
    stage("tomcat deploy code"){
      steps{
//         sshagent(['maven-deploy']) {
//           sh "scp -o StrictHostKeyChecking=no /var/lib/jenkins/workspace/$JOB_NAME/target/*.war ec2-user@54.237.24.49:/opt/apache-tomcat-9.0.72/webapps"
//         }
      }
    }
  }
}
