<h1 align="center">
Linux CLI
</h1>

<p align="center">
<img src="https://readme-typing-svg.herokuapp.com?color=3CBD3A&width=380&height=45&lines=Linux+Command+Line+Interface&center=true"></a>
</p>
<details>
<summary><b>More details</b></summary>
 
- Перемещение в терминале: cd, ls, pwd...
- Работа с файлами: touch, cp, mv, rm, mkdir...
- Работа с текстом: vi, nano... awk, grep, cat, wc...
- Пользователи, права доступа: adduser, usermod, chown, chmod, passwd...
- Мониторинг процессов: ps, top, htop, lsof...
- Работа с сетью:  nmap, netstat, ping, dig, nslookup...
- Производительность системы: nmon, vmstat...
 
 </details>
 
---
> Командный терминал в Linux представляет собой CLI (интерфейс командной строки), где вы вводите команды, которые в противном случае потребовали бы времени с графическим интерфейсом.
---
> Чтобы по-настоящему освоить терминал, вам сначала нужно изучить основы навигации на нем. Мы проведем вас через команды, используемые для навигации по файлам и каталогам, присутствующим в вашей системе Linux. Итак, приступим.
 
<h1 align="center">
:earth_africa:  Советы перед началом
</h1>


- В Оперрационной Системе Linux (Ubuntu) нажимаете на сочетание клавиш `CTRL` + `ALT` + `T` чтобы открыть терминал

<p align="center">
<img src="https://media.giphy.com/media/taVaCpEtQ4B4EPAv66/giphy.gif">
</p>


<p align="center">
В итоге выходит вот такое окно.
</p>

<p align="center">
Внешний вид может отличаться, но команды будут работать так же
</p>

- Обновляем все пакеты в OS (Operating System) командами

> сначала введем в терминал следующее
```
sudo apt-get update -y
```
> потом
```
sudo apt-get upgrade -y
```
> :warning: Зачем прописывать в начале команду `sudo` ? Sudo означает `Super User DO`. Это важная для понимания утилита, она позволяет временно поднимать привилегии и выполнять задачи администрирования системы. Суть в том, что в каждом дистрибутиве Linux есть пользователь root, имеющий максимальные права


