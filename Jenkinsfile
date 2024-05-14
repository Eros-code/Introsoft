pipeline {
    agent any
    tools {
        // Define Docker tool named 'docker' and point it to a Docker installation
        dockerTool 'docker-latest'
    }
    stages {
        stage('Build') {
            agent {
                docker {
                    name 'ansible
                    image 'andrewtarry/ansible:2.13.6'
                    // Run the container on the node specified at the
                    // top-level of the Pipeline, in the same workspace,
                    // rather than on a new node entirely:
                    reuseNode true
                    alwaysPullImage true
                    command 'sleep'
                    args '30d'
                }
            }
        stage('Checkout') {
            steps {
                // Your checkout steps here
                checkout scmGit(branches: [[name: 'main']], extensions: [cloneOption(honorRefspec: true, noTags: true, reference: '', shallow: false), localBranch('main')], userRemoteConfigs: [[credentialsId: 'github-eros-code-IntrosoftDeployKey', url: 'https://github.com/Eros-code/Introsoft.git']])
            }
        }
        stage('Deploy') {
            steps {
                echo 'Hello Jenkins'
            }
        }
    }
}
