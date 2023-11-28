pipeline {
    agent any
    environment {
    PATH = "/opt/apache-maven-3.9.5/bin:${PATH}"
    }    
    stages {
        stage('git clone') {
            steps {
                git 'https://github.com/devopsgagan/project-2.git'
            }
        }
        stage('package build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('test') {
            steps {
                sh 'mvn test'
            }
        }
		stage ('deploy') {
		    steps {
			    deploy adapters: [tomcat9(credentialsId: '945639d7-c3c2-482c-b9d7-d487475654fb', path: '', url: 'http://3.83.50.149:8080/')], contextPath: null, war: '**/*.war'
				}
			}
		}
		post {
		    always {
		        emailext body: '$DEFAULT_CONTENT', subject: '$DEFAULT_SUBJECT', to: 'madeehabanu03@gmail.com'
		    }
		}
	}
