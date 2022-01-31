pipeline {
    agent any

    stages {
        stage('continous download') {
            steps {
                git 'https://github.com/kliakos/sparkjava-war-example.git'
            }
        }
        stage('mvn build') {
            steps {
                sh 'mvn install'
            }
        }
        stage('continues deployment') {
            steps {
                sh 'sshpass -p "vijju" scp target/wwp-1.0.0.war vijju@172.17.0.5:/opt/apache-tomcat-9.0.56/webapps'
            }
        }
    }
}
