pipeline {
    agent any
    stages{
        stage('Build docker image'){
            steps{
                script{
                    sh 'docker build -t garadsnehal98/devops-integration .'
                }
            }
        }
        stage('Push image to Hub'){
            steps{
                script{
                   withCredentials([string(credentialsId: 'dockerhub-pwd', variable: 'dockerhubpwd')]) {
                   sh 'docker login -u garadsnehal98 -p ${dockerhubpwd}'

}
                   sh 'docker push garadsnehal98/devops-integration'
                }
            }
        }
       
    }
}
