node{
    stage("Git Clone"){
        git branch: 'main', credentialsId: 'GIT_HUB_CREDENTIALS', url:'https://github.com/shivasingani/reactdemo.git'
    }
    stage("Docker Build"){
        sh 'docker build -t myfsdcc .'
        sh 'docker image list'
        sh 'docker tag myfsdcc shivasingani/myfsdcc:latest'
    }
    withCredentials([string(credentialsId: 'dockerhub', variable:'password')]){
        sh 'docker login -u shivasingani -p $password'
    }
    stage("Push image to Dockerhub"){
        sh 'docker push shivasingani/myfsdcc:latest'
    }
}