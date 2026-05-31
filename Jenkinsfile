@Library("Shared") _
pipeline{
    agent {label "agent-prvz"}
    
    stages{
        stage("Hello"){
            steps{
                script {
                    hello()
                }
            }
        }
        stage("code"){
            steps{
                script{
                 clone("https://github.com/prvzzz/django-notes-app.git/","main")
                }
            }
        }
        stage("Build"){
            steps{
                script {
                    docker_build("notes-app","latest","prvzzz01")
                }
            }
        }
        stage("Push"){
            steps{
                script{
                    docker_push("notes-app","latest","prvzzz01")
            }
         }
      }
        stage("Deploy"){
             steps {
        echo "this is deploying the code"
        sh "docker compose up -d"
        }
      }
   }
}
