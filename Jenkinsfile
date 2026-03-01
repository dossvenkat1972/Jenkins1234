pipeline {
    agent any

    tools {
        jdk 'JDK25'
        maven 'Maven3'
    }

    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/dossvenkat1972/Jenkins1234.git'
            }
        }

        stage('Build') {
            steps {
                dir('my-app') {
                    bat 'mvn clean package'
                }
            }
        }

        stage('Run') {
            steps {
                dir('my-app') {
                    bat 'dir target'
                    bat 'for %%f in (target\\*.jar) do java -jar %%f'
                }
            }
        }

        stage('Archive') {
            steps {
                archiveArtifacts artifacts: 'my-app/target/*.jar'
            }
        }
    }
}
