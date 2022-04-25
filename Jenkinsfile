pipeline {
    agent any 
      environment {
          DOCKER_CREDS=credentials('docker_id')
    }
    stages{
        stage('build'){
            steps {
                sh 'sudo yum install ansible -y'
            }            
        }
        stage('Deploy'){
            steps{
                sh 'ansible-playbook mongodb-playbook.yml -i hosts -u ec2-user --private-key /tmp/mykp.pem --become'
            }
        }
    }
}