#### Run docker ps every 2 seconds.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
watch docker ps -a
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
#### Logs every 2 seconds
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
watch docker logs idcontainer
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
#### This returns only the sha256:... string and nothing else.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
docker images --no-trunc --quiet nginx:latest
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
#### Kill and Delete Containers and Images
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
docker rmi $(docker images | grep "^<none>" | awk '{print $3}')
docker rm -f $(docker ps -aq)        # Delete all Containers
docker rmi -f $(docker images -q)    # Delete all Images
docker system prune
docker system prune -a -f            # Delete not used containers and images(-f No need to confirm 'y/n')
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
#### how do you disable auto-restart on a container?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
docker update --restart=no my-container
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
#### Remove all unused network
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
docker network prune -f ( -f flag to bypass the prompt. )
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
#### Show all volumes
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
docker volume ls
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
#### Show all volumes size
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
docker system df -v
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
#### Remove volume
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
docker volume rm user_pgdata
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
#### Install Docker on Ubuntu 18.04
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
```
sudo apt update
sudo apt install apt-transport-https
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
sudo apt update
sudo apt install docker-ce
sudo systemctl status docker
sudo usermod -aG docker $USER
>>>logout/login<<<
```
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

#### Sudo user
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
sudo usermod -aG docker $USER
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

#### Inspection
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
docker inspect kda33

cd var/lib/docker
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

#### Docker volumes ( /root/docker/redis - путь на физическом сервере хоста, /data/ - путь внутри контейнера в которую нужно эту папку замонтировать )
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
docker run -- name redis --rm -v /root/docker/redis:/data/ -d redis
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

#### Commands
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
docker run hello-world

docker ps
docker ps -a
docker images

docker search tomcat
docker pull tomcat
docker run -it -p 1234:8080 tomcat
docker run -it -p 8888:80 nginx
docker run -d -p 8888:80 nginx

docker exec -it container_mysql_name mysql -u username -p # To come in container  mysql
docker exec -it 2c6e6ba3d188 mysql -u root -p

docker build -t kda33 .
docker images

docker run -it  -p 1234:80  kda33:latest
docker run -d -p  1234:80  kda33:latest

docker  ps     # list containers
docker  ps -a  # list all containers

docker tag kda33_ubuntu kda33_ubuntu-PROD
docker tag kda33_ubuntu kda33_ubuntu-PROD:v2

docker rm   # delete container
docker rmi  # delete image
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
#### Run docker always
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
sudo systemctl enable docker
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

####  UPDATE IMAGE
~~~~~~~~~~~~~
docker run -d -p 7777:80 kda33_ubuntu4
docker exec -it 5267e21d140 /bin/bash
echo "V2" >> /var/www/html/index.html
exit
docker commit 5267c21d231 kda33_v2:latest
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

#### Export/Import Docker Image to file
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
docker save image:tag > arch_name.tar
docker load -i arch_name.tar
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


#### For Django
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
docker-compose -f prod.yml run --rm web python manage.py collectstatic --no-input
docker-compose -f prod.yml up -d                                                   #Run in deamon
docker-compose -f prod.yml run --rm web python manage.py migrate                   #Migrate for database
docker-compose -f prod.yml run --rm web python manage.py makemigrations            #Makemigrations for database
docker run -v `pwd`:/data --rm -it nameofimage ./                                  #Forward the current directory to this data directory in the container
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

#### Docker-compose
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
docker-compose build - собрать проект
docker-compose up -d - запустить проект в демон режиме
docker-compose down  - остановить проект
docker-compose logs -f [service name] - посмотреть логи сервиса
docker-compose ps - вывести список контейнеров
docker-compose exec [service name] [command] - выполнить команду
docker-compose images - список образов
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
