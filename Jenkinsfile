pipeline {
    agent any

    tools {
        gradle 'Gradle'     // same name as in Jenkins
        jdk 'JDK'         // MUST match your Java 21 config name
    }

    stages {

        stage('Build') {
            steps {
                sh 'echo JAVA_HOME=$JAVA_HOME'
                sh 'java -version'
                sh 'gradle build'
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
