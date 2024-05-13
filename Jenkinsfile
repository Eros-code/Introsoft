pipeline {
    agent {
        docker {image 'andrewtarry/ansible:2.13.6'}
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
                sh "docker run andrewtarry/ansible sleep 30d"
                echo 'Hello Jenkins'
            }
        }
    }
}
