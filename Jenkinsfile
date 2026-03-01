pipeline {
    agent any

    tools {
        jdk 'JDK25'       // Configure in Global Tool Config
        maven 'Maven3'
    }

    environment {
        APP_NAME = "my-app"
    }

    stages {

        stage('Checkout Code') {
            steps {
                git branch: 'main',
                url: 'https://github.com/dossvenkat1972/Jenkins1234.git'
            }
        }

        stage('Verify Workspace') {
            steps {
                bat 'dir'
            }
        }

        stage('Build Project') {
            steps {
                dir('my-app') {
                    bat 'mvn clean package'
                }
            }
        }

        stage('Run Application') {
            steps {
                dir('my-app') {
                    bat 'java -jar target/my-app-1.0.jar'
                }
            }
        }

        stage('Archive Artifact') {
            steps {
                archiveArtifacts artifacts: 'my-app/target/*.jar',
                fingerprint: true
            }
        }
    }

    post {
        success {
            echo 'BUILD SUCCESS ✅'
        }
        failure {
            echo 'BUILD FAILED ❌'
        }
    }
}
