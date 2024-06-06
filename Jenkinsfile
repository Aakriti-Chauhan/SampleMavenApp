pipeline {
    agent any

    tools {
        maven 'Maven' // Name given in Global Tool Configuration
        jdk 'JDK17' // Name given in Global Tool Configuration
    }

    stages {
        stage('Checkout') {
            steps {
			checkout([$class: 'GitSCM', branches: [[name: '*/main']],
                git 'https://github.com/Aakriti-Chauhan/SampleMavenApp.git'
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
