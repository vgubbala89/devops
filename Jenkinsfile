pipeline {
    agent any
    tools { 
        maven 'maven-3.8.6' 
    }
    stages {
        stage('Checkout Git') {
            steps {
                git branch: 'main', url: 'https://github.com/vgubbala89/devops.git'
            }
        }
        
        stage('Build & JUnit Test') {
            steps {
                cd 'home/vgubbala89/devops/demo'
                sh 'mvn install' 
                sh 'mvn package'
            }
            post {
                always {
                    junit 'target/surefire-reports/**/*.xml'
                }
            }
        }
    }
}

