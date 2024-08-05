pipeline {
    agent any

    tools {
        maven 'Maven3' // Install Maven in Jenkins and name it 'Maven3'
        jdk 'JDK11' // Install JDK in Jenkins and name it 'JDK11'
    }

    environment {
        JAVA_HOME = "${tool 'JDK11'}"
        PATH = "${env.PATH};c:/Windows/System32;${env.JAVA_HOME}/bin"
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from the repository
                git branch: 'main', url: 'https://github.com/Mtobasi/MavenExample.git'
            }
        }

        stage('Build') {
            steps {
                // Run Maven build
                bat 'mvn clean install'
            }
        }

        stage('Test') {
            steps {
                // Run Maven tests
                bat 'mvn test'
            }
        }

        stage('Package') {
            steps {
                // Package the application (e.g., create a WAR/JAR file)
                bat 'mvn package'
            }
        }

        stage('Deploy') {
            steps {
                // Deployment steps (e.g., copy the WAR file to a server)
                // Uncomment and modify according to your deployment strategy
                // bat 'scp target/your-app.war user@server:/path/to/deploy'


                // Placeholder for deployment steps
                                echo 'Deployment step would go here.'
            }
        }
    }

    post {
        success {
            echo 'Build and deployment succeeded!'
        }
        failure {
            echo 'Build or deployment failed!'
        }
    }
}