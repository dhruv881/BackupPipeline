pipeline {
    agent any
    parameters {
        string(name: 'BACKUP_DESTINATION', defaultValue: '/home/ubuntu/folder2', description: 'Destination path where to copy the backup')
    }
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
                ansiblePlaybook(
                    installation: 'Ansible',
                    playbook: 'backup_script.yml',
                    extraVars: [
                        backup_directory: "${params.BACKUP_DESTINATION}"
                    ]
                )
            }
        }
    }
}
