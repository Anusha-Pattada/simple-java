// File: Jenkinsfile

pipeline {
    agent any
    
    environment {
        REPO_URL = 'https://github.com/your-user/hello-world-java-app.git'
        BRANCH = 'main'
    }
    
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                script {
                    // Run Maven Build
                    sh 'mvn clean package'
                }
            }
        }

        stage('Docker Build and Push') {
            steps {
                script {
                    // Build Docker image
                    sh 'docker build -t yourdockerhub/hello-world-java-app .'
                    // Push Docker image to registry
                    sh 'docker push yourdockerhub/hello-world-java-app'
                }
            }
        }

        stage('Deploy to Tomcat') {
            steps {
                script {
                    // Deploy to Tomcat server using Ansible
                    sh 'ansible-playbook -i inventory deploy_tomcat.yml'
                }
            }
        }
    }
}
