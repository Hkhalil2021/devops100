pipeline {
    agent any

    environment {
        IMAGE_NAME = "devops-httpd"
        IMAGE_TAG  = "v1"
    }

    stages {

        stage('Docker-Verify') {
            steps {
                sh 'docker --version'
            }
        }

        stage('Git-Verify') {
            steps {
                sh 'git --version'
            }
        }

        stage('Docker-Build') {
            steps {
                sh '''
                    echo "Building Docker image..."
                    echo "Image: ${IMAGE_NAME}:${IMAGE_TAG}"

                    ls -la
                    docker build -t ${IMAGE_NAME}:${IMAGE_TAG} .

                    echo "Docker images:"
                    docker images | head -n 10
                '''
            }
        }
    }
}
