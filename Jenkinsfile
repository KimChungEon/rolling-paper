node {
    stage('Clone repository') {
        git credentialsId: 'git-token', url: 'https://github.com/KimChungEon/rolling-paper.git' , branch: 'main'
    }

    stage('Build image') {
        dockerImage = docker.build("chungeon/node-front:1.0", ".")
    }

    stage('Push image') {
            withDockerRegistry([ credentialsId: "docker-acccess", url: "" ]) {
                dockerImage.push()
        }

    }
}