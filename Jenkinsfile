pipeline {
    agent any
    environment {
        DOCKERHUB_CREDENTIALS = credentials('docker-hub-credentials')
        DOCKERHUB_DEV_REPO = 'sridharsdocker/react-app-dev'
        DOCKERHUB_PROD_REPO = 'sridharsdocker/react-app-prod'
        GIT_REPO_URL = 'https://github.com/sridhar667/Devops-Project.git'
    }

    stages {
        stage('Checkout Code') {
            steps {
                // Checkout the code from the Git repository
                git branch: env.BRANCH_NAME, url: "${GIT_REPO_URL}"
            }
        }
        stage('Build Docker Image') {
            steps {
                sh './build.sh'
            }
        }
        stage('Push to Docker Hub') {
            when {
                anyOf {
                    branch 'dev'
                    branch 'master'
                }
            }
            steps {
                script {
                    docker.withRegistry('https://registry.hub.docker.com', ${DOCKERHUB_CREDENTIALS}) {
                        if (env.BRANCH_NAME == 'dev') {
                            // Push the Docker image to the dev repository on Docker Hub
                            sh "docker push ${DOCKERHUB_DEV_REPO}:${BRANCH_NAME}_latest"
                        } else if (env.BRANCH_NAME == 'master') {
                            // Push the Docker image to the prod repository on Docker Hub
                            sh "docker tag ${DOCKERHUB_DEV_REPO}:dev_latest ${DOCKERHUB_PROD_REPO}:latest"
                            sh "docker push ${DOCKERHUB_PROD_REPO}:latest"
                        }
                    }
                }
            }
        }
       stage('Deploy') {
          steps {
                sh './deploy.sh'
            }
        }
    }
    post {
        success {
            echo 'Docker image successfully built and pushed to Docker Hub!'
        }
        failure {
            echo 'Build or push failed.'
        }
    }
}
