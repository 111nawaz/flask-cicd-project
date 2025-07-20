pipeline {
    agent any

    environment {
        DOCKER_IMAGE = 'nawaz1114/flask-cicd-app'
        IMAGE_TAG = 'v1'
        DOCKER_CREDENTIALS_ID = 'docker-hub-creds'
    }

    stages {
        stage('Clone Repo') {
            steps {
                echo "Cloning repository..."
                git branch: 'main', url: 'https://github.com/111nawaz/flask-cicd-project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                echo "Building Docker image..."
                sh "docker build -t $DOCKER_IMAGE:$IMAGE_TAG ."
            }
        }

        stage('Push to Docker Hub') {
            steps {
                echo "Pushing Docker image to Docker Hub..."
                withDockerRegistry([credentialsId: "$DOCKER_CREDENTIALS_ID", url: ""]) {
                    sh "docker push $DOCKER_IMAGE:$IMAGE_TAG"
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                echo "Running Docker container..."
                sh "docker rm -f flask-container || true"
                sh "docker run -d --name flask-container -p 5001:50pipeline {
    agent any

    environment {
        DOCKER_IMAGE = 'nawaz1114/flask-cicd-app'
        IMAGE_TAG = 'v1'
        DOCKER_CREDENTIALS_ID = 'docker-hub-creds'
    }

    stages {
        stage('Start Message') {
            steps {
                echo "🚀 Pipeline started successfully"
            }
        }

        stage('Clone Repo') {
            steps {
                echo "🔄 Cloning repo..."
                git branch: 'main', url: 'https://github.com/111nawaz/flask-cicd-project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                echo "🐳 Building Docker image..."
                sh "docker build -t $DOCKER_IMAGE:$IMAGE_TAG ."
            }
        }

        stage('Push to Docker Hub') {
            steps {
                echo "📦 Pushing Docker image..."
                withDockerRegistry([credentialsId: "$DOCKER_CREDENTIALS_ID", url: ""]) {
                    sh "docker push $DOCKER_IMAGE:$IMAGE_TAG"
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                echo "🚀 Running Docker container..."
                sh "docker rm -f flask-container || true"
                sh "docker run -d --name flask-container -p 5001:5000 $DOCKER_IMAGE:$IMAGE_TAG"
            }
        }
    }
}

