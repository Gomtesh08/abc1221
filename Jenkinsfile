pipeline {
    agent any

    environment {
        // Define Java Home if necessary (example for OpenJDK 11)
        JAVA_HOME = '/usr/lib/jvm/java-11-openjdk-amd64'
        PATH = "${JAVA_HOME}/bin:${PATH}"
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from GitHub
                git branch: 'main', url: 'https://github.com/your-username/your-repo-name.git'
            }
        }

        stage('Compile') {
            steps {
                script {
                    // Compile the HelloWorld.java file
                    sh 'javac HelloWorld.java'
                }
            }
        }

        stage('Run') {
            steps {
                script {
                    // Run the compiled Java program
                    sh 'java HelloWorld'
                }
            }
        }
    }

    post {
        always {
            // Actions to perform after the build finishes, regardless of success or failure
            echo 'Build completed.'
        }

        success {
            // Actions to perform if the build succeeds
            echo 'HelloWorld program ran successfully.'
        }

        failure {
            // Actions to perform if the build fails
            echo 'Build or execution failed.'
        }
    }
}
