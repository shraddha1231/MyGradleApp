pipeline {
    agent any

    tools {
        gradle 'Gradle'
        jdk 'JDK'   // must point to Java 21 in Jenkins
    }

    stages {

        stage('Build') {
            steps {
                sh 'echo JAVA_HOME=$JAVA_HOME'
                sh 'java -version'
                sh 'gradle clean build'
            }
        }

        stage('Test') {
            steps {
                sh 'gradle test'
            }
        }

        stage('Run Application') {
            steps {
                sh 'gradle run'
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
