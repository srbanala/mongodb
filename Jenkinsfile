pipeline {
    agent any 
      environment {
          DOCKER_CREDS=credentials('docker_id')
    }
    stages{
        stage('build'){
            steps {
                sh 'python pip install ansible'
            }
            
        }
    }
}