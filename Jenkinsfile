pipeline {
    agent any 
      environment {
          DOCKER_CREDS=credentials('docker_id')
    }
    parameters {
        string( name: 'address',defaultValue: '10.0.2.224' ,description: 'MongoDbServer')
    }
    stages{
        stage('build'){
            steps {
                sh 'sudo yum install ansible -y'
            }            
        }
        stage('Test'){
            steps{
               sh ' ssh ec2-user@"${address}" -i /tmp/mykp.pem '
            }
        }
        stage('Deploy'){
            steps{
                sh 'ansible-playbook mongodb-playbook.yml -i hosts -u ec2-user --private-key /tmp/mykp.pem --become'
            }
        }
    }
}