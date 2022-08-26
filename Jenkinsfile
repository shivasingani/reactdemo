node{
    stage("Git Clone"){
        git branch: 'main', credentialsId: 'GIT_HUB_CREDENTIALS', url:'https://github.com/shivasingani/reactdemo.git'
    }
    stage("Docker Build"){
        sh 'docker version'
    }
}