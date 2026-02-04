@Library("Shared") _
pipeline{
    
    agent { label "agent1"}
    
    stages{
        stage("Code"){
            steps{
                script{
                    clone("https://github.com/Siddhesh-hub/django-notes-app.git","dev")
                }
            }
        }
        stage("Build"){
            steps{
                script{
                    docker_build("notes-app", "latest", "SiddheshP1410")
                }
            }
        }
        stage("Push to DockerHub"){
            steps{
                script{
                    docker_push("notes-app", "latest", "SiddheshP1410")
                }
            }
        }
        stage("Deploy"){
            steps{
                script{
                    docker_decompose()
                }
            }
        }
    }
}
