sudo apt update
sudo apt-get install docker.io
sudo apt install git
sudo apt nano
//gitbash-git init,git add . ,git commit -m "first commit"
 git branch -M main
git remote add origin https://github.com/preethigugulothu/awsexample.git
git push -u origin main
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





