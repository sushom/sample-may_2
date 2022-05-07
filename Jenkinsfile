pipeline {
    agent any
    tools {
        maven "M3"
    }
    stages {
        stage('Build') {
            steps {
                git 'https://github.com/kul-boa/sample-may.git'
                sh "mvn clean install"
            }
            post {
                success {
                    archiveArtifacts 'target/*.war'
                }
            }
        }
        stage('Deploy') {
            sh 'cp target/my-webapp.war ~/tomcat/webapps/sushom.war'
        }    
    }
}
