pipeline {
    agent any
    
    tools {
        jdk 'JDK25'
        maven 'Maven3'
    }

    stages {

        stage('Checkout') {
    steps {
        git branch: 'main',
            url: 'https://github.com/dossvenkat1972/Jenkins1234.git'
    }
}
       

       stage('Build') {
            steps {
                dir('my-app') {
                    bat 'mvn clean compile'
                }
            }
        }

        stage('Test') {
            steps {
                 dir('my-app') {
                    bat 'mvn clean compile'
                }
            }
        }

        stage('Package') {
            steps {
                bat 'mvn -e -X package'
            }
        }

        stage('Archive Artifact') {
            steps {
                archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
            }
        }
    }
}
