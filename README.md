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

