pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'running build automation'
                sh 'ansible-playbook -i /etc/ansible/hosts /etc/ansible/switch_configs.yml'
                 }
            }
        }
    } 
