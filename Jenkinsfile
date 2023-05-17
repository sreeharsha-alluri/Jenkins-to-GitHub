pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                script {
                    docker.image('nginx:latest').pull()
                    docker.image('nginx:latest').inside {
                        sh 'apt-get update && apt-get install -y git'
                        git url: 'https://github.com/sreeharsha-alluri/Jenkins-to-GitHub.git'
                        sh 'docker build -t my-nginx-image . -f Dockerfile'
                    }
                }
            }
        }
    }
}
