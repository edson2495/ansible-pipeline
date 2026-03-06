pipeline {
    
    agent {
        docker {
            image 'alpine/ansible:2.20.0'
            args '-u root:root'
        }
    }

    stages {
        stage('ansible') {
            steps {

                //sh 'whoami'
                sh 'ansible --version'

                sshagent(credentials: ['amazon-linux-private-key']){

                    sh 'ansible server1 -i hosts -m ping -u ec2-user' 

                }
                
            }
        }
    }
}