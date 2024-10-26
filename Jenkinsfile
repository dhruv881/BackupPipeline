pipeline {
    agent any
    environment {
        ANSIBLE_HOST = 'localhost'
    }
    stages {
        stage('Checkout') {
            steps {
                git credentialsId: 'github-token', url: 'https://github.com/dhruv881/BackupPipeline.git', branch: 'main'
            }
        }
        
        stage('Run Backup Script with Ansible') {
            steps {
                ansiblePlaybook installation: 'Ansible', playbook: 'backup_script.yml'
            }
        }
    }
}
