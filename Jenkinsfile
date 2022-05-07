pipeline {
    agent any
    tools {
        maven "M3"
    }
    stages {
        stage('Build') {
            steps {
                git 'https://github.com/sushom/sample-may_2.git'
                sh "mvn clean install"
            }
            post {
                success {
                    archiveArtifacts 'target/*.war'
                }
            }
        }
        stage('Deploy') {
            steps {
                sh 'cp target/my-webapp.war ~/tomcat/webapps/sushom.war'
            }    
        }    
    }
}
