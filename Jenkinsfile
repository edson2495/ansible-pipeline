pipeline {
    
    agent {
        docker {
            image 'alpine/ansible:2.20.0'
            args '-u root:root'
        }
    }

    environment {
        ANSIBLE_HOST_KEY_CHECKING = 'False'
    }

    stages {
        stage('ansible') {
            steps {

                //sh 'whoami'
                sh 'ansible --version'

                sshagent(credentials: ['amazon-linux-private-key']){

                    // sh 'ansible server1 -i hosts -m ping -u ec2-user'

                    // sh 'ansible server1:server2:server3 -i hosts -m ping -u ec2-user'

                    // sh 'ansible groupA -i hosts -m ping -u ec2-user'

                    // sh 'ansible all -i hosts -m ping -u ec2-user'

                    sh 'ansible server1 -i hosts -m command -a "cat /etc/os-release" -u ec2-user'
                    // sh 'ansible server1 -i hosts -a "cat /etc/os-release" -u ec2-user'

                    // sudo yum install tree -y
                    // sh 'ansible server1 -i hosts -m yum -a "name=tree state=latest" -u ec2-user'
                    // sh 'ansible server1 -i hosts -m yum -a "name=tree state=latest" -u ec2-user --become'

                    // sudo yum remove tree -y
                    // sh 'ansible server1 -i hosts -m yum -a "name=tree state=absent" -u ec2-user --become'

                    // sh 'ansible server1 -i hosts -m ansible.builtin.yum -a "name=nmap state=latest" -u ec2-user --become'

                    // sh 'ansible-inventory -i hosts --graph'

                    // sh 'ansible-playbook -i hosts playbooks/server1_config.yml'

                    // sh 'ansible-playbook -i hosts playbooks/server1_jboss.yml'

                }
                
            }
        }
    }
}