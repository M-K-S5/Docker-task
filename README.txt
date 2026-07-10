===[ repo Setup ]===

mkdir "Docker Task 1"
cd Docker Task 1
git init
touch README.txt
git remote add origin https://github.com/M-K-S5/Docker-task.git
git add .
git commit -m "init"
git push -u origin master
git commit -am "added submission guidelines"
git push

===[ Part 1 ]===

docker pull alpine
docker run -d --name alpine_sleeper alpine sleep 1000
docker ps -a 
docker stop alpine_sleeper
docker rm alpine_sleeper
docker rmi alpine

===[ Part 2 ]===

docker pull ubuntu
docker run -d --name ubuntu-server ubuntu sleep 1000
docker exec ubuntu-server 'while true; do echo "Input website:"; read website; echo "Searching.."; sleep 1; curl http://$website; done'
docker exec -it ubuntu-server bash
apt update
apt install curl
