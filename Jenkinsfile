pipeline{
    agent any
    stages{
        stage('Checkout SCM'){
            steps{
                git url: 'https://github.com/Karthikg99/example-voting-app.git'
            }
        }
        stage('Ansible Docker installation'){
            steps{
                sh "ansible-playbook -i hosts azure_docker.yml"
                sh "sleep 30"
            }
        }
        stage('Ansible Minikube installation'){
            steps{
                sh "ansible-playbook -i hosts minikube.yml"
            }
        }
        stage('Ansible Kubernetes Cluster deployment'){
            steps{
                sh "ansible-playbook -i hosts ansible-mminikube.yml"
            }
        }
    }
}
