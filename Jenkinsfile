pipeline {
    agent any 
    stages {
        stage('Build') {
            steps {
               echo "Building the application..."
               sh 'mvn clean package' 
            }
        }
    }
      
