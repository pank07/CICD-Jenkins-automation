pipeline {
    agent { label "Agent-1" }

    stages {
        stage("Code") {
            steps {
                git url: 'https://github.com/pank07/django-notes-app.git', branch: "main", credentialsId: 'github-PAT'
                echo "Code cloned successfully"
            }
        }

        stage("Build") {
            steps {
                echo "Building the code"
                sh '''
                    set -ex
                    whoami
                    docker build -t notes-app:latest .
                    docker images
                '''
            }
        }

        stage("Test") {
            steps {
                echo "Testing the code"
                // Add actual test commands if needed
            }
        }

        stage("Push to DockerHub") {
            steps {
                echo "Pushing the image to DockerHub"
                withCredentials([usernamePassword(
                    credentialsId: "DockerHubCred",
                    usernameVariable: 'DOCKERHUB_USER',
                    passwordVariable: 'DOCKERHUB_PASS'
                )]) {
                    sh '''
                        set -ex
                        echo "$DOCKERHUB_PASS" | docker login -u "$DOCKERHUB_USER" --password-stdin
                        docker image tag notes-app:latest "$DOCKERHUB_USER/notes-app:latest"
                        docker push "$DOCKERHUB_USER/notes-app:latest"
                    '''
                }
            }
        }

        stage("Deploy") {
            steps {
                echo "Deploying the code"
                sh '''
                    set -ex
                    docker-compose --version
                    docker-compose down
                    docker-compose up -d
                '''
            }
        }
    }
}
