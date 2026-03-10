pipeline {
    agent any

    tools {
        jdk 'JDK17'
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
                sh 'mvn clean package'
            }
        }

        stage('Verify Artifact') {
            steps {
                sh 'ls target'
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
