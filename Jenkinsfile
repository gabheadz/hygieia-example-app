pipeline {
    agent any
    environment {
        GRADLE_USER_HOME = "$WORKSPACE/.gradle"
        HOME="/var/jenkins_home"
    }
    stages {
        stage('Build') {
            steps {
                sh './gradlew build'
            }
        }
        stage('SonarQube') {
            steps {
                sh './gradlew -Dsonar.host.url=http://sonarqube:9000 jacocoTestReport sonarqube'
            }
        }
    }
}
