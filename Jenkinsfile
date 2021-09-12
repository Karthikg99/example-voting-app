pipeline{
    agent any
    stages{
        stage('Checkout SCM'){
            steps{
                git url: 'https://github.com/Karthikg99/example-voting-app.git'
            }
        }
        stage('Build Vote docker image and push'){
            steps{
//                 sh "cd vote/"
                sh "docker build -t karthikg99/python-voter-app ./vote"
                sh "docker login --username=karthikg99 --password=Krookedk@99"
                sh "docker push karthikg99/python-voter-app"
            }
        }
        stage('Build Result docker image and push'){
            steps{
//                 sh "cd .."
//                 sh "cd result/"
                sh "docker build -t karthikg99/node-result-app ./result"
                sh "docker push karthikg99/node-result-app"
            }
        }
        stage('Build Worker docker image and push'){
            steps{
//                 sh "cd .."
//                 sh "cd worker/"
                sh "docker build -t karthikg99/java-worker-app ./worker"
                sh "docker push karthikg99/java-worker-app"
            }
        }
            
//         stage('Ansible Docker installation'){
//             steps{
//                 sh "ansible-playbook -i hosts azure_docker.yml"
//                 sh "sleep 30"
//             }
//         }
//         stage('Ansible Minikube installation'){
//             steps{
//                 sh "ansible-playbook -i hosts minikube.yml"
//             }
//         }
//         stage('Ansible Kubernetes Cluster deployment'){
//             steps{
//                 sh "ansible-playbook -i hosts ansible-minikube.yml"
//             }
//         }
    }
}
