pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/ADITYA310802/Food-image-identification.git'
            }
        }
        
        stage('Build') {
            steps {
                withGradle {
                    sh './gradlew clean build'
                }
            }
        }
        
        stage('Test') {
            steps {
                withGradle {
                    sh './gradlew test'
                }
            }
        }
        
        stage('Deploy') {
            steps {
                withGradle {
                    sh './gradlew deploy'
                }
            }
        }
    }
    
    post {
        always {
            junit '**/build/test-results/test/*.xml'
        }
    }
}

