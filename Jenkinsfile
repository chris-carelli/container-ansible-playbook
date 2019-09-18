pipeline {
    agent any
    stages {
        stage('ping dev') {
            steps {
                echo 'running ping tests'
                sh 'ansible -m ping arista215'
            }
        }
        stage('Build to dev') {
            when {
                branch 'master'
            }    
            steps {
                echo 'running build automation'
                sh 'ansible-playbook -i hosts vxlan-playbook.yml'
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
                 sh 'ansible-playbook -i hostsf5 /etc/ansible/f5_create_vpm.yml'
             }
         }
     }
}  
