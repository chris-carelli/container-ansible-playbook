pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'running build automation'
                sh 'ansible-playbook -i hosts:arista215/etc/ansible/switch_configs.yml'
                 }
            }
        }
    } 
