pipeline {
    agent any
    stages {
        stage('ping dev') {
            steps {
                echo 'running ping tests'
                sh 'ansible all -m ping -i hosts'
            }
        }
        stage('Build to dev') {
            when {
                branch 'master'
            }    
            steps {
                echo 'running build automation'
                sh 'ansible-playbook -i hosts /etc/ansible/switch_configs.yml'
                 }
            }
        }
    stage('deploy to F5s') {
        when {
            branch 'master'
        }
        steps {
            echo 'running F5 build'
            sh 'ansible-playbook -i hostsf5 /etc/ansible/f5_script_to_activate.yml
        }
    }
}
