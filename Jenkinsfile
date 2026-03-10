pipeline {
    agent any

    tools {
        maven 'Maven'
        jdk 'JDK21'
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
                bat 'dir target'
            }
        }
    }

    post {
        failure {
            echo 'Build FAILED'
        }
        success {
            echo 'Build SUCCESS'
        }
    }
}