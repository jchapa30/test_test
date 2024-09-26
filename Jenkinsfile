pipeline {
    agent any  
    tools {
        maven 'Maven' // Make sure you have Maven installed and configured in Jenkins
    }
    stages {
        stage('Build jar') {
            steps {
                script {
                    echo "Building application"
                    sh 'mvn package' // Maven command to package the application
                }
            }
        }
        stage('Build image') {
            steps {
                script {
                    echo "Building Docker image"
                    withCredentials([usernamePassword(credentialsId: 'docker-hub-repo', passwordVariable: 'PASS', usernameVariable: 'USER')]) {
                        sh '''
                        docker build -t jchapa30/test-test:1 .
                        docker login -u $USER -p $PASS
                        docker push jchapa30/test-test:1
                        '''
                    }
                }
            }
        }
        stage('Test') {
            steps {
                echo 'Running tests'
                // Add test commands or scripts here
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying application'
                // Add deployment commands or scripts here
            }
        }
    }
}

