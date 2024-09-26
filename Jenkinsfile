pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the application'
                // Add build commands here, such as Maven or Gradle build commands
                // sh 'mvn clean package' or similar
            }
        }
       
        stage('Test') {
            steps {
                echo 'Running tests'
                // Add test commands here, such as unit tests
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'Deploying application'
                // Add deployment commands here, such as deploying to a server or Docker
            }
        }
    }
}
