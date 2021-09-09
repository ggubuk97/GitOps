pipeline {
  agent any
  stages {
    stage('git pull') {
      steps {
        // git@github.com:ggubuk97/GitOps.git will replace by sed command before RUN
        git url: 'https://github.com/ggubuk97/GitOps.git', branch: 'main'
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
