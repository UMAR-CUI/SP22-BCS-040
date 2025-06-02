pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/UMAR-CUI/SP22-BCS-040.git'
            }
        }
        
        stage('Build') {
            steps {
                sh 'javac hello.java'  // compile hello.java to hello.class
            }
        }
        
        stage('Deploy') {
            steps {
                // Example deploy path - change if needed
                sh 'mkdir -p $WORKSPACE/deploy/helloApp'
                sh 'cp hello.class $WORKSPACE/deploy/helloApp/'
            }
        }

        stage('Run') {
            steps {
                sh 'java -cp /var/deploy/helloApp hello'
            }
        }
    }
}
