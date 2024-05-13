podTemplate(containers: [
    containerTemplate(
        name: 'ansible', 
        image: 'andrewtarry/ansible', 
        command: 'sleep', 
        args: '30d')
  ]) {

    node(POD_LABEL) {
        stage('Step') {
            container('ansible') {
                stage('Checkout') {
                    checkout([$class: 'GitSCM', branches: [[name: '*/main']], userRemoteConfigs: [[url: 'git@github.com:Eros-code/Introsoft.git', credentialsId: 'github-eros-code-introsoftDeployKey']]])
                }
                stage('Deploy') {
                    sh "echo Hello Jenkins"
                }
            }
        }
    }

  }
