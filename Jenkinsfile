pipeline {
    agent {
        docker {
            // Specify the Docker image to use
            image 'andrewtarry/ansible'
        }
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
                sh 'echo Hello Jenkins'
            }
        }
    }
}
