#-------------------------------------------------
# Introduction to Docker
Install Docker on Ubuntu 18.04
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

#### Kill and Delete Containers and Images
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
docker rm -f $(docker ps -aq)        # Delete all Containers
docker rmi -f $(docker images -q)    # Delete all Images
docker system prune
docker system prune -a               # Delete not used containers and images
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

#### For Django
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
docker-compose -f prod.yml run --rm web python manage.py collectstatic --no-input
docker-compose -f prod.yml up -d                                                   #Run in deamon
docker-compose -f prod.yml run --rm web python manage.py migrate                   #Migrate for database
docker-compose -f prod.yml run --rm web python manage.py makemigrations            #Makemigrations for database
docker run -v `pwd`:/data --rm -it nameofimage ./                                  #Forward the current directory to this data directory in the container
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~