pipeline {
    agent any
    stages {
        stage('ping dev') {
            steps {
                echo 'running ping tests'
                sh 'ansible -m ping eos215'
            }
        }
        stage('Build to dev') {
            when {
                branch 'master'
            }    
            steps {
                echo 'running build automation'
                sh 'ansible-playbook -i /etc/ansible/hosts_for_eos_roles /etc/ansible/eossite215.yml'
              }
           }
         stage('deploy to F5s') {
             when {
                 branch 'master'
             }
             steps {
                 input 'Did the arista config go in?'
                 milestone(1)
                 echo 'running F5 build'
                 sh 'ansible-playbook -i /etc/ansible/hosts.yml /etc/ansible/f5_script_node.yml'
             }
         }
     }
}  
