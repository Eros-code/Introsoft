pipeline {
    agent any
    tools {
        // Define Docker tool named 'docker' and point it to a Docker installation
        dockerTool 'docker-latest'
    }
    stages {
        stage('Checkout') {
            steps {
                // Your checkout steps here
                checkout scmGit(branches: [[name: 'main']], extensions: [cloneOption(honorRefspec: true, noTags: true, reference: '', shallow: false), localBranch('main')], userRemoteConfigs: [[credentialsId: 'github-eros-code-IntrosoftDeployKey', url: 'https://github.com/Eros-code/Introsoft.git']])
            }
        }
        stage('Deploy') {
            steps {
                script{
                    // Define Docker image and options
                    def dockerImage = 'andrewtarry/ansible:2.13.6'
                    def dockerOptions = "--rm -i -v ${pwd()}:/workspace"
                    // Run commands inside the Docker container
                    sh "docker run ${dockerOptions} ${dockerImage} /bin/bash -c 'sleep 30d'"
                    sh "docker run ${dockerOptions} ${dockerImage} /bin/bash -c 'echo Deploying...'"
                }
                echo 'Hello Jenkins'
            }
        }
    }
}
