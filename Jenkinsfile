pipeline{
  agent {
    label 'master'
  }
  environment {
    ssh_private_key = "/var/lib/jenkins/.ssh/id_rsa"
  }
    stages{
        stage('Build') {
            steps{
                sh 'ls'
                sh 'pwd'
                sh 'cd /home/ubuntu/app_code'
                sh 'npm install'
            }
        }
        stage('Deploy') {
            steps {
                script {
                    sh '''
                    ansible-playbook nodejs_deploy.yml -i ./hosts --private-key=${ssh_private_key} -e host="all" --ssh-common-args="-o StrictHostKeyChecking=no"
                    '''
                }
            }
        }
    }
}
