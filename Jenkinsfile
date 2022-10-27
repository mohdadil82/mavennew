pipeline {
    agent any

    triggers {
         pollSCM('* * * * *') // Polling Source Control
     }

stages{
        stage('Build'){
        when {
            branch 'main'
            steps {
                sh 'mvn install'
            }
            post {
                success {
                    echo 'copying artifacts to tomcat9'
                    sh 'cp **/* /var/lib/tomcat9/webapps/'
                }
            }
        }
        }
        
        stage('Build1'){
        when {
            branch 'branch1'
            steps {
                sh 'mvn install'
            }
            post {
                success {
                    echo 'copying artifacts to tomcat9'
                    sh 'cp **/* /ops/tomcat8/webapps/'
                }
            }
        }
        }
      

  } 
}
