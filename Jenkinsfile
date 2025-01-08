node {
    stage('Clone repository') {
        git credentialsId: 'github-token', url: 'https://github.com/KimChungEon/rolling-paper.git'
    }

    stage('Build image') {
        dockerImage = docker.build("chungeon/node-front:1.0")
    }

    stage('Push image') {
            withDockerRegistry([ credentialsId: "docker-access", url: "" ]) {
            dockerImage.push()
        }

    }
}