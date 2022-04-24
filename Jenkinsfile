pipeline {
    agent any 
      environment {
          DOCKER_CREDS=credentials('docker_id')
    }
    stages{
        stage('build'){
            steps {
                sh 'yum install pip'
                sh 'python pip install ansible'
            }
            
        }
    }
}