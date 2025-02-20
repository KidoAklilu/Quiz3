pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/KidoAklilu/Quiz3.git' 
            }
        }
        
        stage('Build') {
            steps {
                script {
                    sh 'mvn clean install'
                }
            }
        }
        
        stage('Test') {
            steps {
                script {
                    sh 'mvn test'
                }
            }
        }

        stage('Code Coverage') {
            steps {
                script {
                    sh 'mvn jacoco:report'
                }
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'Deploying to the server' 
            }
        }
    }
}
