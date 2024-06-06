pipeline {
    agent any

    tools {
        maven 'Maven' // Ensure this matches the name configured in Global Tool Configuration
        jdk 'JDK17' // Ensure this matches the name configured in Global Tool Configuration
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Aakriti-Chauhan/SampleMavenApp.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
    }

    post {
        success {
            echo 'Build and Test succeeded!'
        }
        failure {
            echo 'Build or Test failed.'
        }
    }
}
