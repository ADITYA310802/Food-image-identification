pipeline {
    agent any
    
    tools {
        gradle 'Gradle' // specify the Gradle installation name configured in Jenkins
    }
    
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/ADITYA310802/Food-image-identification.git'
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
                sh './gradlew test'
            }
        }
        
        stage('Deploy') {
            steps {
                sh './gradlew deploy'
            }
        }
    }
    
}
