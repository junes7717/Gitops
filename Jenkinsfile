pipeline {
  agent any
  stages {
    stage('git pull') {
      steps {
        // https://github.com/junes7717/Gitops.git will replace by sed command before RUN
        git url: 'https://github.com/junes7717/Gitops.git', branch: 'main'
      }
    }
    stage('k8s deploy'){
      steps {
        kubernetesDeploy(kubeconfigId: 'kubeconfig',
                         configs: '*.yaml')
      }
    }    
  }
}