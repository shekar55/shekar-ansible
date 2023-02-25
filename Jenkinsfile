pipeline{
    agent any
    stages{
        stage ('SCM Checkout'){
            steps {
                checkout scmGit(branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: 'git', url: 'https://github.com/shekar55/shekar-ansible.git']])
            }
        }
        stage('Execute Ansible'){
            steps{
                ansiblePlaybook credentialsId: 'ubuntu11', disableHostKeyChecking: true, installation: 'ansible', inventory: 'dev.inv', playbook: 'apache.yml'
                }
        }
            
    }    
}
