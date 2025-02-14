pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                // Clone the repository from GitHub.
                git url: 'https://github.com/masked-devil/jenkins-task5', branch: 'master'
            }
        }
        
        stage('Build') {
            steps {
                // Compile the Java program. Ensure the command is correct.
                sh 'javac src/TimestampPrinter.java'
            }
        }
        
        stage('Run') {
            steps {
                // Run the Java program. Adjust the classpath if needed.
                sh 'java -cp src TimestampPrinter'
            }
        }
    }
    
    triggers {
        // Poll for SCM changes (you may also use GitHub webhooks)
        pollSCM('* * * * *')
    }
}
