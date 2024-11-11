pipeline {
    agent any

    environment {
        // Set JAVA_HOME to the location of the Java installation
        JAVA_HOME = 'C:\\Program Files\\Java\\jdk-21'  // Adjust based on your JDK installation path
        PATH = "${JAVA_HOME}\\bin;${PATH}"
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout code from GitHub
                git branch: 'main', url: 'https://github.com/Gomtesh08/abc1221.git'
            }
        }

        stage('Compile') {
            steps {
                script {
                    // Compile the Java program using javac (Windows command)
                    bat 'javac HelloWorld.java'
                }
            }
        }

        stage('Run') {
            steps {
                script {
                    // Run the Java program using java (Windows command)
                    bat 'java HelloWorld'
                }
            }
        }
    }

    post {
        always {
            echo 'Build completed.'
        }

        success {
            echo 'HelloWorld program ran successfully.'
        }

        failure {
            echo 'Build or execution failed.'
        }
    }
}
