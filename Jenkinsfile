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
                // Your deployment steps here
                sh "docker run andrewtarry/ansible sleep 30d"
                echo 'Hello Jenkins'
            }
        }
    }
}
