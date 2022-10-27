pipeline {
    agent any
  
    stages {
        stage('Clean') {
            steps {
                sh 'mvn clean'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn install'
            }
        }
        stage('production') {
            when {
                branch 'main'
            }
            steps {
                sh 'cp **/* /var/lib/tomcat9/webapps/h'
            }
        }
        stage('Testing-branch') {
            when {
                branch 'branch1'
            }
            steps {
                sh 'cp **/* /ops/tomcat8/webapps/'
            }
        }
    }
}
