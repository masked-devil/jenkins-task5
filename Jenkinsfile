pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                // Pull the code from GitHub
                git url: 'https://github.com/masked-devil/jenkins-task5', branch: 'main'
            }
        }
        
        stage('Build') {
            steps {
                // Compile the Java program
                sh 'javac TimestampPrinter.java'
            }
        }
        
        stage('Run') {
            steps {
                // Run the Java program
                sh 'java TimestampPrinter'
            }
        }
    }
    
    triggers {
        // This trigger checks for changes periodically (every minute)
        pollSCM('* * * * *')
    }
}
