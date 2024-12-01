pipeline{

    agent any

    stages{

        stage("Code"){
            steps{
              echo "cloning....."
              git url : "https://github.com/VarshaRajS/web-application-deployment-using-nginx.git", branch : "main"
            }
        }
        stage("Build"){
            steps{
              echo "building....."
              sh "docker build -t my-app ."
            }
        }
        stage("Push to DockerHub"){
            steps{
                withCredentials([usernamePassword("credentialsId":"dockerHub", usernameVariable : "dockerHubUser", passwordVariable : "dockerHubPass")]){
                  sh "docker tag my-app ${env.dockerHubUser}/my-app:latest"
                  sh "docker login -u ${env.dockerHubUser} -p ${env.dockerHubPass}"
                  sh "docker push ${env.dockerHubUser}/my-app:latest"
                }
            }
        }
        stage("Deploy"){
            steps{
                echo "This is deploying the code........"
                sh "docker-compose down && docker-compose up"
            }
        }
    }
}
