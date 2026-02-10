pipeline{
  agent {label "${LABEL_NAME}"}
  
  stages{
    stage('code') {
      steps {
        git url:"https://github.com/Huzefa211/Ansible_Jenkins.git" , branch: "main"
      }
    }
       stage('ANSIBLE PLAYBOOK') {
      steps {
                ansiblePlaybook(
                  playbook: 'ansible/deploy.yml',
                  inventory: 'ansible/host.ini',
                  credentialsId: "${SSH_KEY}"
                )
      }
    }
  } 
}
