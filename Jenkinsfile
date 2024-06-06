pipeline {
    agent any
    tools {
        jdk 'JDK17' // Ensure this matches the name configured in Jenkins
        maven 'Maven' // Ensure this matches the name configured in Jenkins
    }
    stages {
        stage('Checkout') {
            steps {
                // Correctly formatted checkout step
                git branch: 'main', url: 'https://github.com/Aakriti-Chauhan/SampleMavenApp.git'
            }
        }
        stage('Build') {
            steps {
                // Build steps
                sh 'mvn clean install'
            }
        }
        stage('Test') {
            steps {
                // Test steps
                sh 'mvn test'
            }
        }
    }
    post {
        failure {
            echo 'Build or Test failed.'
        }
    }
}
