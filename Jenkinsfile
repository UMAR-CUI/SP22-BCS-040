pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'javac src/hello.java'
            }
        }

        stage('Deploy') {
            steps {
                sh 'mkdir -p "$WORKSPACE/deploy"'
                sh 'cp src/hello.class "$WORKSPACE/deploy/"'
            }
        }

        stage('Run') {
            steps {
                sh 'java -cp "$WORKSPACE/deploy" hello'
            }
        }
    }
}
