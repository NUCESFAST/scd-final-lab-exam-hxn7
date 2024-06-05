pipeline {
    agent any  // Run on any available agent

    stages {
        stage('21i1123 Checkout Code') {
            steps {
                git branch: 'main', // 
                    url: 'https://github.com/NUCESFAST/scd-final-lab-exam-hxn7'  // Public repo, no credentials needed
            }
        }
        stage('21i1123 Build Docker Image for Auth') {
            steps {
                script {
                    sh 'docker build -t auth-api:1 ./Auth' 
                }
            }
        }
       

        stage('21i1123 Build Docker Image for Classrooms') {
            steps {
                script {
                    sh 'docker build -t classrooms-api:1 ./Classrooms'  
                }
            }
        }
        

        stage('21i1123 Build Docker Image for Client') {
            steps {
                script {
                    sh 'docker build -t client-web:1 ./client'  
                }
            }
        }
        

        stage('21i1123 Build Docker Image for EventBus') {
            steps {
                script {
                    sh 'docker build -t eventbus-api:1 ./event-bus'  // Replace placeholders
                }
            }
        }
        

        stage('21i1123 Build Docker Image for Post') {
            steps {
                script {
                    sh 'docker build -t post-api:1 ./Post'  // Replace placeholders
                }
            }
        }
        
    }
}
