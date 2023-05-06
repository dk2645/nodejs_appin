pipeline{
  agent {
    label 'master'
  }
  environment {
    project_dir = ""
    ssh_private_key = "/home/jenkins/.ssh/id_rsa"
  }
    stages{
        stage('Build') {
            steps{
                sh 'ls'
                sh 'pwd'
                sh 'npm install'
            }
        }
        stage('Managing ACLs') {
            steps {
                script {
                    sh '''
                    ansible-playbook nodejs_deploy.yml -i /path/hosts --private-key=${ssh_private_key} -e host="all" --ssh-common-args="-o StrictHostKeyChecking=no"
                    '''
                }
            }
        }
    }
}
