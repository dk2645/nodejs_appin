pipeline{

    agent any

    stages {
        
        

        stage("build") {

            steps {
            echo "building the application"
            
            }

        }


        stage("deploying") {

            steps {
            echo "deploying the application"
            git credentialsId: 'a27287d7-6998-4db5-90ca-60b551e7fca1', url: 'https://github.com/awsandgit/nodejs-code.git'
            ansiblePlaybook become: true, credentialsId: '3422ea1b-c84f-4f88-b240-9d1cfbe4edb7', installation: 'ansible', inventory: '/var/lib/jenkins/workspace/ansible-playbook/inventory', playbook: '/var/lib/jenkins/workspace/ansible-playbook/myplay1.yml'
            }

        }

    }

}
