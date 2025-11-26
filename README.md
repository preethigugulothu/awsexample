sudo apt update
sudo apt-get install docker.io
sudo apt install git
sudo apt nano
//gitbash-git init,git add . ,git commit -m "first commit"
 git branch -M main
git remote add origin https://github.com/preethigugulothu/awsexample.git
git credential-manager reject https://github.com
git config --global --unset credential.helper
git push -u origin main
////dockerfile
FROM nginx:alpine
COPY . /usr/share/nginx/html

//cmd
git clone https://github.com/preethigugulothu/awsexample.git
docker build -t mywebapp .
docker run -d -p 80:80 mywebapp
docker ps
//////NGIOS
docker pull jasonrivers/nagios:latest
docker start -ai nagios4
docker run --name nagiosdemo -p 8888:80 jasonrivers/nagios:latest
Enter username : nagiosadmin 
Enter password : nagios
////jenkinscript
pipeline {
    agent any
    tools{
        maven 'MAVEN-HOME'
    }
    stages {
        stage('git repo & clean') {
            steps {
                //bat "rmdir  /s /q mavenjava"
                bat "git clone provide your github link"
                bat "mvn clean -f mavenjava"
            }
        }
        stage('install') {
            steps {
                bat "mvn install -f mavenjava" #project name#
            }
        }
        stage('test') {
            steps {
                bat "mvn test -f mavenjava"
            }
        }
        stage('package') {
            steps {
                bat "mvn package -f mavenjava"
            }
        }
    }
}
/////////////kubernetes
minikube start
minikube status
kubectl get deployments
kubectl create deployment mynginx --image=nginx
kubectl scale deployment mynginx --replicas=4
kubectl expose deployment mynginx --type=NodePort --port=80 --target-port=80
kubectl get service mynginx
kubectl port-forward svc/mynginx 8081:80






