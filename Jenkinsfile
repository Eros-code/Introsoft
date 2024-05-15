podTemplate(inheritFrom: 'ansible', containers: [
    containerTemplate(
        name: 'ansible',
        image: 'andrewtarry/ansible:2.13.6')
  ]) {
node(POD_LABEL) {
    stage('Deploy') {
          container('ansible') {
                stage('Checkout') {
                    steps {
                        // Your checkout steps here
                        checkout scmGit(branches: [[name: 'main']], extensions: [cloneOption(honorRefspec: true, noTags: true, reference: '', shallow: false), localBranch('main')], userRemoteConfigs: [[credentialsId: 'github-eros-code-IntrosoftDeployKey', url: 'https://github.com/Eros-code/Introsoft.git']])
                    }
                }
                stage('Deploy') {
                    steps {
                        sh "echo Hello Jenkins"
                    }
                }
            }
        }
    }
}
