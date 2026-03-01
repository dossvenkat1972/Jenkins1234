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
        }

        stage('Build') {
            steps {
                bat 'mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                bat 'mvn test'
            }
        }

        stage('Package') {
            steps {
                bat 'mvn package'
            }
        }

        stage('Archive Artifact') {
            steps {
                archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
            }
        }
    }
}
