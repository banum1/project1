pipeline {
    agent any
    environment {
    PATH = "/opt/apache-maven-3.9.5/bin:${PATH}"
    }    
    stages {
        stage('Build the Package') {
            steps {
                // Building the package using Maven
                sh 'mvn clean package'
            }
        }
        stage('Test the Package') {
            steps {
                // Testing the package using Maven Test
                sh 'mvn test'
            }
        }
    }
}
