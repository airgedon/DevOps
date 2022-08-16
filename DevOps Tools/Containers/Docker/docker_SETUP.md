<h1 align="center">
Установка
</h1>

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
