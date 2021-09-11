pipeline{
    agent any
    stages{
        stage('Checkout SCM'){
            steps{
                git url: 'https://github.com/Karthikg99/example-voting-app.git'
            }
        }
        stage('Ansible Checking'){
            steps{
                sh "ansible-playbook ansible-copy.yml"
            }
        }
    }
}
