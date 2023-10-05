pipeline {
    agent any

    stages {
        stage('code') {
            steps {
                git credentialsId: '007ec968-be46-4dbe-83f7-c5b3ffbc0e64', url: 'https://github.com/sunildevops77/maven.git'
            }
        }
		stage('compile') {
            steps {
                sh 'mvn compile'
            }
        }
    stage('package') {
            steps {
                sh 'mvn package'
            }
        }
	stage('deploy') {
            steps {
                deploy adapters: [tomcat9(credentialsId: '007ec968-be46-4dbe-83f7-c5b3ffbc0e64', path: '', url: 'http://18.60.115.207:8081/')], contextPath: 'sai', war: '**/*.war'
            }
        }
	}
	
}
