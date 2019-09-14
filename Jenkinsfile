
pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'running build automation'
                sh 'ansible-playbook -i hosts switch_configs.yml'
                     }
                }
            }
        } 
