pipeline{
    agent any

    stages{
        stage("Build Stage"){
            steps{
                echo "Building docker stage"
                sh "docker build -t devopsaditya123/newapp:v1 . "
            }
        }

        stage("push to Docker Hub"){
            steps{
                echo "Pushing Image to Docker hub"
                withCredentials([usernamePassword(credentialsId: 'docker-hub-pass', passwordVariable: 'PASS', usernameVariable: 'USER')]){
                      sh 'echo $PASS | docker login -u $USER --password-stdin'
                      sh "docker push devopsaditya123/newapp:v1"
                }
            }
        }

}
}