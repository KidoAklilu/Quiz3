pipeline {
    agent any
tools {
        maven 'Maven' 
    }
triggers {
        cron('H 10 * * 1') 
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/KidoAklilu/Quiz3.git'
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
