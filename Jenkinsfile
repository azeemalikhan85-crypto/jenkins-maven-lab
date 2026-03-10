pipeline {
    agent any

    tools {
        jdk 'JDK21'
        maven 'Maven3'
    }

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                bat 'mvn clean package'
            }
        }

        stage('Verify Artifact') {
            steps {
                bat 'ls target'
            }
        }
    }

    post {
        success {
            echo 'Build SUCCESSFUL'
        }
        failure {
            echo 'Build FAILED'
        }
    }
}
