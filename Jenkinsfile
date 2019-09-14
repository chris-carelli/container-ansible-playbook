pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'running build automation'
                sh 'ansible-playbook /etc/ansible/switch_configs.yml'
                 }
            }
        }
    } 
