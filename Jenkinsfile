@Library('library_name')_
pipeline{
    agent { label 'vinod'}
    
    stages{
        stage("Code clone"){
            steps{
                sh "whoami"
            clone("https://github.com/TarakSonawane/django-notes-app.git","main")
            }
        }
        stage("Code Build"){
            steps{
            docker_build("notes-app","latest","tarak13")
            }
        }
        stage("Push to DockerHub"){
            steps{
                docker_push("DockerHubID","notes-app")
            }
        }
        stage("Deploy"){
            steps{
                sh "docker compose up -d"
            }
        }
        
    }
}
