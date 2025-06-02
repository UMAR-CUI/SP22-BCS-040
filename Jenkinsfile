pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Pull latest code from GitHub (change URL to your repo)
                git branch: 'main', url: 'https://github.com/UMAR-CUI/SP22-BCS-040.git'
            }
        }
        
        stage('Build') {
            steps {
                // Compile hello.java
                sh 'javac hello.java'
            }
        }
        
        stage('Test') {
            steps {
                // Run the program to verify it works (optional)
                sh 'java hello'
            }
        }
        
        stage('Deploy') {
            steps {
                sh 'mkdir -p /var/deploy/helloApp'
                sh 'cp Hello.class /var/deploy/helloApp/'
            }
        }
    }
    
    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed.'
        }
    }
}
