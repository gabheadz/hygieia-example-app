pipeline {
    agent any
    environment {
        HOME="/var/jenkins_home"
        GRADLE_USER_HOME = "$WORKSPACE/.gradle"
        SONAR_USER_HOME = "$WORKSPACE/.sonar"
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
