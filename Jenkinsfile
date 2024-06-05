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
                    sh 'docker build -t auth-api:1 .' 
                }
            }
        }
        stage('21i1123 Push Auth to Docker Hub') {
            steps {
                script {
                    withCredentials([usernamePassword(credentialsId: 'dockerhub-credentials')]) {
                        sh 'docker login -u $USERNAME -p $PASSWORD'
                        sh 'docker tag auth-api:1 $USERNAME/auth-api:1'
                        sh 'docker push $USERNAME/auth-api:1'
                    }
                }
            }
        }

        stage('21i1123 Build Docker Image for Classrooms') {
            steps {
                script {
                    sh 'docker build -t classrooms-api:1 .'  
                }
            }
        }
        stage('21i1123 Push Classrooms to Docker Hub') {
            steps {
                script {
                    withCredentials([usernamePassword(credentialsId: 'dockerhub-credentials')]) {
                        sh 'docker login -u $USERNAME -p $PASSWORD'
                        sh 'docker tag classrooms-api:1 $USERNAME/classrooms-api:1'
                        sh 'docker push $USERNAME/classrooms-api:1'
                    }
                }
            }
        }

        stage('21i1123 Build Docker Image for Client') {
            steps {
                script {
                    sh 'docker build -t client-web:1 .'  
                }
            }
        }
        stage('21i1123 Push Client to Docker Hub') {
            steps {
                script {
                    withCredentials([usernamePassword(credentialsId: 'dockerhub-credentials')]) {
                        sh 'docker login -u $USERNAME -p $PASSWORD'
                        sh 'docker tag client-web:1 $USERNAME/client-web:1'
                        sh 'docker push $USERNAME/client-web:1'
                    }
                }
            }
        }

        stage('21i1123 Build Docker Image for EventBus') {
            steps {
                script {
                    sh 'docker build -t eventbus-api:1 .'  // Replace placeholders
                }
            }
        }
        stage('21i1123 Push EventBus to Docker Hub') {
            steps {
                script {
                    withCredentials([usernamePassword(credentialsId: 'dockerhub-credentials')]) {
                        sh 'docker login -u $USERNAME -p $PASSWORD'
                        sh 'docker tag eventbus-api:1 $USERNAME/eventbus-api:1'
                        sh 'docker push $USERNAME/eventbus-api:1'
                    }
                }
            }
        }

        stage('21i1123 Build Docker Image for Post') {
            steps {
                script {
                    sh 'docker build -t post-api:1 .'  // Replace placeholders
                }
            }
        }
        stage('21i1123 Push Post to Docker Hub') {
            steps {
                script {
                    withCredentials([usernamePassword(credentialsId: 'dockerhub-credentials')]) {
                        sh 'docker login -u $USERNAME -p $PASSWORD'
                        sh 'docker tag post-api:1 $USERNAME/post-api:1'
                        sh 'docker push $USERNAME/post-api:1'
                    }
                }
            }
        }
    }
}
