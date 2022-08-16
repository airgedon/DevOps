<h1 align="center">
Docker Commands
</h1>
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

