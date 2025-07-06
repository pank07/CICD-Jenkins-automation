@Library("Shared@main") _
pipeline {
    agent { label "Agent-1" }
    stages {
        stage("hello"){
            steps{
                script{
                    hello()
                }
            }
        }
        stage("Code") {
            steps {
                script{
               clone("https://github.com/pank07/django-notes-app.git","main")
            }
            }
        }
        stage("Build") {
            steps {
                script{
                    docker_build("notes-app","latest","pank04")
                }
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
                script{
                    docker_push("notes-app","latest","pank04")
                }
                }
        }
        stage("Deploy") {
            steps {
                echo "Deploying the code"
                     sh "docker compose down && docker compose up -d "
            }
        }
    }
}
                                    
