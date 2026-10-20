pipeline{
    agent any
     stages{
        stage("1 Build Stage"){
            steps{
                echo "this is Build Stages of Image"
                sh "docker build -t devopsaditya123/fileapp:v1 ."
            }
        }
        stage('this is push stage'){
            steps{
                withCredentials([usernamePassword(credentialsId:"docker-hub-pass", passwordVariable: "PASS" , usernameVariable: "USER")]){
                       sh "echo $PASS | docker login -u $USER --password-stdin"
                       sh "docker push devopsaditya123/fileapp:v1"
                }
            }
        }
     }
}