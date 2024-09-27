pipeline {
  agent any
  stages {
    stage('git pull') {
      steps {
        // https://github.com/sseregit/GitOps-practice.git will replace by sed command before RUN
        git url: 'https://github.com/sseregit/GitOps-practice.git', branch: 'main'
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