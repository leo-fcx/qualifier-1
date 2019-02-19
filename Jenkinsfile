pipeline {
    agent { docker { image 'maven:3-alpine' } }
    stages {
        stage('build') {
            steps {
                sh 'mvn clean'
            }
        }
        stage('build') {
            steps {
                sh 'mvn compile'
            }
        }
        stage('test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('package') {
            steps {
                sh 'mvn package'
                script { 
                  docker.build("timoteoponce/qualifier")
                }
            }
        }
    }
}