pipeline {
    agent any
    environment {
        GRADLE_USER_HOME = "$WORKSPACE/.gradle"
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
