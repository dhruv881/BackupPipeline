pipeline {
    agent any
    environment {
        ANSIBLE_HOST = 'localhost'
    }
    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/yourusername/yourrepo.git'
            }
        }
        
        stage('Run Backup Script with Ansible') {
            steps {
                ansiblePlaybook installation: 'Ansible', playbook: 'backup_script.yml'
            }
        }
    }
}
