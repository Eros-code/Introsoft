podTemplate(containers: [
    containerTemplate(
        name: 'node', 
        image: 'node:18', 
        command: 'sleep', 
        args: '30d')
  ]) {

    node(POD_LABEL) {
        stage('Step') {
            container('node') {
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
