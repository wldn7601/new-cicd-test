pipeline {
    agent any

    environment {
        logFile = "/tmp/java_output.log"
    }

    stages {
        stage('Github Pull') {
            steps {
                git branch: 'main', url: 'https://github.com/wldn7601/new-cicd-test.git'
            }
        }

        stage('Compile') {
            steps {
                sh 'javac src/Main.java'
            }
        }

        stage('Run') {
            steps {
                sh "java -cp src Main | tee ${env.logFile}"
            }
        }
    }
}

