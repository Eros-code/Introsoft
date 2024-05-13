pipeline {
    agent any
    environment {
        DOCKER_HOME = tool name: 'docker', type: 'org.jenkinsci.plugins.docker.commons.tools.DockerTool'
    }
    stages {
        stage('Checkout') {
            steps {
                // Your checkout steps here
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], userRemoteConfigs: [[url: 'git@github.com:Eros-code/Introsoft.git', credentialsId: 'github-eros-code-introsoftDeployKey']]])
            }
        }
        stage('Deploy') {
            steps {
                // Your deployment steps here
                sh "${DOCKER_HOME}/bin/docker run andrewtarry/ansible sleep 30d"
                echo 'Hello Jenkins'
            }
        }
    }
}
