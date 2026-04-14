pipeline {
    agent any

    tools {
        gradle 'Gradle'
        jdk 'JDK'   // must point to Java 21 in Jenkins tool config
    }

    stages {

        stage('Clean') {
            steps {
                sh './gradlew clean || gradle clean'
            }
        }

        stage('Build') {
            steps {
                sh 'echo JAVA_HOME=$JAVA_HOME'
                sh 'java -version'
                sh './gradlew build || gradle build'
            }
        }

        stage('Test') {
            steps {
                sh './gradlew test || gradle test'
            }
        }

        stage('Run Application') {
            steps {
                sh './gradlew run || gradle run'
            }
        }
    }

    post {
        success {
            echo 'Build and deployment successful!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
