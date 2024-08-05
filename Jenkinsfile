pipeline {
    agent any

    tools {
        maven 'Maven3' // Install Maven in Jenkins and name it 'Maven3'
        jdk 'JDK11' // Install JDK in Jenkins and name it 'JDK11'
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
                sh 'mvn clean install'
            }
        }

        stage('Test') {
            steps {
                // Run Maven tests
                sh 'mvn test'
            }
        }

        stage('Package') {
            steps {
                // Package the application (e.g., create a WAR/JAR file)
                sh 'mvn package'
            }
        }

        stage('Deploy') {
            steps {
                // Deployment steps (e.g., copy the WAR file to a server)
                // Uncomment and modify according to your deployment strategy
                // sh 'scp target/your-app.war user@server:/path/to/deploy'


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