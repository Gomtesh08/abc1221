pipeline {
    agent any

    environment {
        // Define Java Home if necessary, here we assume OpenJDK 11
        JAVA_HOME = '/usr/lib/jvm/java-11-openjdk-amd64'
        PATH = "${JAVA_HOME}/bin:${PATH}"
    }

    stages {
        stage('Checkout') {
            steps {
                // Pull the code from your GitHub repository
                git branch: 'main', url: 'https://github.com/your-username/your-java-app.git'
            }
        }

        stage('Build') {
            steps {
                script {
                    // Run Maven to clean, compile, test, and package the application
                    sh 'mvn clean install'
                }
            }
        }

        stage('Run Application') {
            steps {
                script {
                    // Assuming the built JAR is in the target directory
                    // Run the Java application (replace 'your-app-name.jar' with your actual JAR file name)
                    sh 'java -jar target/your-app-name.jar'
                }
            }
        }
    }

    post {
        always {
            // This will always run, even if the build fails
            echo 'Build completed.'
        }

        success {
            // If the build is successful, we can perform additional actions
            echo 'Build and application run completed successfully.'
        }

        failure {
            // If the build fails, this will notify or take action
            echo 'Build or application run failed.'
        }
    }
}
