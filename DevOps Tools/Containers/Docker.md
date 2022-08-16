<h1 align="center">
:earth_africa: DOCKER
</h1>  

<p align="center">
<img src="https://readme-typing-svg.herokuapp.com?color=3CBD3A&width=380&height=45&lines=Что+такое+Docker+?&center=true"></a>
</p>

<p align="center">
Docker - это по сути маленькие виртуальные машины, изолированные среды и в этих изолированных средах мы можем запускать разные проекты на разных языках программирования на одном сервере
</p>

<h2 align="center">
Установка
</h2>

```
sudo apt-get update && apt-get upgrade
```
```
sudo apt install apt-transport-https ca-certificates curl software-properties-common
```
```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```
```
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"
```
```
sudo apt update
```
```
apt-cache policy docker-ce  
```
```
sudo apt install docker-ce
```
<h3 align="center">
Готово, Docker установлен
</h3>

#### Проверяем статус докера
```
sudo systemctl status docker
```
<p align="center">
<img src="https://media.giphy.com/media/zFbzovmEHorfmvQmIR/giphy.gif">
</p>

> клавиша `q` для выхода

<h2 align="center">
Настройка работы команды docker без sudo 
</h2>

```
sudo usermod -aG docker ${USER}
```
```
su - ${USER}
```
```
id -nG
```
> вывод:    your_username sudo docker
```
sudo usermod -aG docker username
```
<h2 align="center">
Установка docker-compose
</h2>
 
```
sudo curl -L "https://github.com/docker/compose/releases/download/1.26.0/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
```
```
sudo chmod +x /usr/local/bin/docker-compose
```
```
docker-compose -v
```
> to stop docker-compose
```
docker-compose stop
```
# Docker Commands
____
```
docker build .
```
> #### -it = interactive, -d - close image in opened status
```
docker run -itd (name or id)        
```
> create own image
docker build -t name_of_new_image .
> then it`ll appear in:
```
docker images
```
> So how to run container with the name "system" with your own created image
```
docker run --name system name_of_new_image
```
> run container with the name "system" with your own created image with using port
```
docker run --name system -p 8001:8001 -d name_of_new_image
```
____
> needed to pull images from docker.hub
```
docker pull (id)
```

```
sudo chmod 666 /var/run/docker.sock
```

```
docker stop (id)
```

```
docker start (id)
```
> #### -p = port
```
docker run -p 8000:8000 (id)      
```
> to list all present images
```
docker images
```
> to list all present containers
```
docker container ls 
```
> or
```
docker ps
```
> #### -a = all (all active and inactive containers)
```
docker ps -a                      
```
---
> WARNING: Image for service web was built because it did not already exist. To rebuild this image you must use:  
```
docker-compose build
```
> or
```
docker-compose up --build
```
___
#### DELETE
> to delete container
```
docker container rm (id)
```
> This will remove all stopped containers
```
docker contаiner prune
```
```
docker system prune
```
```
docker rmi (id)
```

```
docker kill $(docker ps -q)
```

> #### to delete all images  -f = force
```
docker rmi -f $(docker images -q)         
```
___
```
docker exec -it 4a23c4bdaae3 python3 manage.py createsuperuser
```
```
docker exec -it 4a23c4bdaae3 python3 manage.py migrate
```
```
docker exec -it 4a23c4bdaae3 python3 manage.py makemigrations
```
```
docker exec -it 4a23c4bdaae3 python3 manage.py createsuperuser
```
---
[Steps for Deploying a Static HTML Site with Docker and Nginx](https://www.dailysmarty.com/posts/steps-for-deploying-a-static-html-site-with-docker-and-nginx)
---
> in docker-compose.yml (maybe to use several django containers)
```
# under volumes
ports:
  - 5435:5432
```

