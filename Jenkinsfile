pipeline {
    agent any

    tools {
        maven 'Maven 3'
    }

    stages {
        stage('Build') {
            steps {
                sh 'mvn clean package'
                archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
            }
        }

        stage('Test') {
            steps {
                junit 'target/surefire-reports/*.xml'
            }
        }
    }
}
