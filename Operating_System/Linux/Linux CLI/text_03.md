<h1 align="center">
Работа с текстом
</h1>

- Работа с текстом: vi, nano, awk, grep, cat, wc
---
# :bulb: Команда «nano»
>  Nano - текстовый редактор для терминала.

Если Nano у вас не установлен, установить его можно командой:
```
sudo apt update
```
```
sudo apt install nano
```
>  Команда выше подходит для операционных систем Debian/Ubuntu.

Чтобы открыть существующий файл или создать новый, в командной строке наберите nano и название файла:
```
nano apple.txt
```

<p align="center">
<img src="https://media.giphy.com/media/XRWwPuQXPqFXWL5Lt5/giphy.gif">
</p>
 
Так же можно сделать чтобы при изменения файла создавалась его резервная копия. Для этого используется ключ -B:

```
nano -B apple.txt
```

> :mag_right: После сохранения файла будет создана резервная копия файла с содержимым, которое было до изменения. Имя резервной копии соответствует имени исходного файла со значком тильды ~ на конце.
---
> Сразу после открытия редактора вы можете приступить к редактированию файла 
#### Сохранение и выход
Если вам нужно сохранить изменения и выйти из редактора, то используйте сочетание клавиш:
```
Ctrl+X
```
Дальше, если вы изменяли файл, то появится вопрос: **«Save modified buffer?»**. Если вы хотите сохранить изменения нажмите клавишу **Y**, появится вопрос на ввод имени файла. Введите новое имя файла или оставьте старое и нажмите **Enter**. Если не хотите сохранять изменения, то нажмите клавишу **N**.
# :bulb: Команда «vi»
> Vi - альтернатива текстового редактора для терминала **nano**

Чтобы открыть существующий файл или создать новый, в командной строке наберите vi и название файла:
```
vi apple.txt
```
Вы всегда начинаете в режиме редактирования, поэтому первое, что мы собираемся сделать, это переключиться в режим вставки, нажав i

<p align="center">
<img src="https://media.giphy.com/media/NMJBgLMmH9PusLfvms/giphy.gif">
</p>

Теперь введите несколько строк текста и нажмите клавишу Esc, и вы вернетесь в режим редактирования.

### **Сохранение и выход**

<details>
<summary><b>More details (Click me!)</b></summary>
 
- ZZ — Сохранить и выйти
- :q! — отменить все изменения, начиная с последнего сохранения, и выйти
- : w — сохранить файл, но не выходить
- : wq — снова сохранить и выйти
</details>

> :mag_right: Большинство команд в vi выполняются, как только вы нажимаете последовательность клавиш. Любая команда, начинающаяся с двоеточия (:), требует, чтобы вы нажали «Enter» для завершения команды.

<p align="center">
<img src="https://media.giphy.com/media/4m4mht8sNbwfBIyGPF/giphy.gif">
</p>

# :bulb: Команда «cat»
> Сat используется для просмотра текстовых файлов (меньше содержимого)
```
cat [параметры] [файл]
```
- cat -n отобразить номер строки

- cat -b похож на -n, разница в том, что -b не нумерует пустые строки.
---

<p align="center">
<img src="https://media.giphy.com/media/Kv8c4SS26tUXnQY6Xk/giphy.gif">
</p> 

# :bulb: Команда «awk»

> AWK – это скриптовый язык, который полезен при работе в командной строке и широко применяется для обработки текста.

> :mag_right: При использовании awk вы можете выбирать данные – один или более отдельных фрагментов текста – на основе заданного критерия. Например, с помощью awk можно выполнять поиск конкретного слова или шаблона во фрагменте текста, а также выбирать определённую строку/столбец в файле.

Чтобы использовать awk, введите следующее:
```
awk '{action}' avocado.txt
```
Когда вам нужно найти текст, соответствующий конкретному шаблону, или же конкретное слово в тексте, команда принимает следующий вид:

```
awk '/regex pattern/{action}' avocado.txt
```
Для вывода всего содержимого файла в качестве действия в фигурных скобках нужно указать print $0:
```
awk '{print $0}' avocado.txt
```

<p align="center">
<img src="https://media.giphy.com/media/bm6snpHxescq2w354w/giphy.gif">
</p> 

Если захотите добавить нумерацию строк, то нужно будет дополнить действие переменной NR:
```
awk '{print NR,$0}' avocado.txt
```
> :mag_right: При использовании awk можно указывать для вывода конкретные столбцы.

- Вывод первого производится следующей командой:
```
awk '{print $1}' avocado.txt
```
Здесь $1 означает первое поле, то есть в данном случае первый столбец.
- Для вывода второго столбца используется $2:
```
awk '{print $2}' avocado.txt
```
> :mag_right: По умолчанию начало и конец каждого столбца awk определяет по пробелу.
- Для вывода большего числа столбцов, например, первого и четвёртого, нужно выполнить:
```
awk '{print $1, $3}' avocado.txt
```
> Здесь $1 представляет первое поле ввода (первый столбец), а $4 четвёртое. При этом они отделяются запятой, чтобы вывод разделялся пробелом и был более читаемым.
- Для вывода последнего поля (последнего столбца) также можно использовать команду $NF, представляющую последнее поле записи:

<p align="center">
<img src="https://media.giphy.com/media/DMIAWnC78IiNIycCZw/giphy.gif">

Также можно указывать для вывода строку определённого столбца:
```
awk '{print $1}' avocado.txt | head -1
```
> :mag_right: Разделим эту команду на две части. Сначала awk '{print $1}' information.txt выводит первый столбец. Затем её результат (который мы видели выше) с помощью символа | передаётся на обработку команде head, где аргумент -1 указывает на выбор первой строки столбца.
-Для вывода двух строк команда будет такой:
```
awk '{print $2}' avocado.txt | head -1
```
 
<p align="center">
<img src="https://media.giphy.com/media/9VnaYOSYX5UHbBZM7O/giphy.gif">
</p> 

Вы можете выводить строку, начинающуюся с заданной буквы. Например:
```
awk '/^b/' avocado.txt
```
Эта команда выбирает все строки с текстом, начинающимся на O.
> :mag_right: Действие команды начинается с символа ^, который указывает на начало строки. После этого прописывается буква, с которой нужная вам строка должна начинаться.

- По аналогичному принципу можно выводить строку, завершающуюся конкретным шаблоном:
```
awk '/g$/' avocado.txt
```
> Эта команда выводит строки, оканчивающиеся на 0 – здесь с помощью символа $ мы указываем, как должна заканчиваться нужная строка.
- При этом её можно несколько изменить:
```
awk '! /g$/' avocado.txt 
```
> :mag_right: Символ ! используется в качестве приставки «НЕ», а значит, в этом случае будут выбраны строки, которые не оканчиваются на 0.

<p align="center">
<img src="https://media.giphy.com/media/StyQZJU9H357KxZQv8/giphy.gif">
</p> 

- Для вывода слов, содержащих определённые буквы, а также слов, соответствующих указанному шаблону, мы снова используем прямые слэши.

К примеру, если нас интересуют слова, содержащие io, мы пишем:
```
awk ' /med/{print $0}' avocado.txt
```

<p align="center">
<img src="https://media.giphy.com/media/xYkXkMHWujs2N7OppC/giphy.gif">

Мы получили строки, в которых содержатся слова, содержащие med.
> Теперь предположим, что в файле есть дополнительный столбец LOCATION:

<p align="center" width="100%">
    <img src="https://github.com/airgedon/DevOps/blob/main/Operating_System/Linux/Linux%20CLI/PNG/Screenshot%20from%202022-08-12%2013-37-54.png"> 
</p>

Для поиска всей информации о фруктах, находящихся к примеру в box, нужно указать искомую строку между //:
```
awk '/box/' avocado.txt
```
> А что, если мы хотим увидеть только цвет и название фруктов которые находятся в коробке ( box )?

Тогда можно указать столбец так:
```
awk '/box/{print $1, $2}' avocado.txt
```

<p align="center">
<img src="https://media.giphy.com/media/1Rod8kw3rwebpj7l9j/giphy.gif">
</p> 

В этом случае отобразятся только первый и второй столбцы строк, содержащих box.
- При поиске слов, содержащих конкретный шаблон, бывают случаи, когда требуется использовать экранирующий символ:
```
awk '/home\/kitchen$/' avocado.txt
```

<p align="center">
<img src="https://media.giphy.com/media/UNFNzVAtq8gTxLTu1k/giphy.gif">
</p>

при указании критериев поиска в ' // ', как это показывалось выше, мне пришлось использовать между home/kitchen символ перехода \. В противном случае возникла бы ошибка.

#### Добавим ещё один столбец "AMOUNT" 

<p align="center" width="100%">
    <img src="https://github.com/airgedon/DevOps/blob/main/Operating_System/Linux/Linux%20CLI/PNG/Screenshot%20from%202022-08-12%2013-50-50.png"> 
</p>

> :mag_right: Если вы, предположим, захотите найти всю информацию о фруктов в количестве от 10 штук, то нужно будет использовать оператор сравнения > так:
```
awk '$5 > 10 { print $0 }' avocado.txt
```

<p align="center">
<img src="https://media.giphy.com/media/EHKWkfcFgmXrQ2WET8/giphy.gif">
</p> 

В выводе представлена информация о фруктах количество которых больше 10.

# :bulb: Команда «grep»
> Команда grep даёт пользователям возможность вести поиск строки. 

> :mag_right: С его помощью можно даже искать конкретные слова в файле. Также можно передать вывод любой команды в grep, что сильно упрощает работу во время поиска и траблшутинга. 

если нужно найти конкретную папку или один файл среди сотни других, то мы можем передать вывод команды ls в grep через вертикальную черту (|), а уже grep-у параметром передать нужное слово.
```
ls | grep fruits
```
Если команда grep ничего не вернула, значит искомого файла/папки не существует в данной директории.

<p align="center">
<img src="https://media.giphy.com/media/OKEzmtiz6KhxzRq3iM/giphy.gif">
</p> 

> :mag_right: Если же нужно найти не одно слово, а словосочетание или целое предложение, то параметр команды grep должно быть выделено кавычками. Grep поддерживает как одинарные, так и двойные кавычки.
```
ls | grep 'My Fruits'
```
A также его можно использовать так:
```
grep 'apple tree' avocado.txt
```
В этом примере мы вели поиск указанных в кавычках слов в файле avocado.txt и команда grep успешно справилась со своей задачей.

<p align="center">
<img src="https://media.giphy.com/media/MqHMA5GWKBnWlgZ9lc/giphy.gif">
</p> 

> :mag_right: Команде grep можно передавать не один параметр, а несколько.
 
 Для этого перед каждым аргументом пишется ключ e. Эту команду система понимает, как "или-или" и выводит все вхождения указанных слов. Заметьте, что кавычками выделена только строка, которая содержит пробел. 
```
grep -e 'apple tree' -e 'green avocado' avocado.txt
```

<p align="center">
<img src="https://media.giphy.com/media/P7pr1jhhEF9aIwlpxL/giphy.gif">
</p> 

> :mag_right:  egrep это тоже самое, что и grep E (помните, командная строка Linux регистрозависимая и команды grep e и grep E интерпретируются по разному).

- То есть, к при
- 
- меру, две команды ниже эквивалентны и выводят все строки, в которых есть две подряд идущих буквы "p".

```
egrep 'e|e' avocado.txt

grep -E 'p|p' avocado.txt
```

<p align="center" width="100%">
    <img src="https://github.com/airgedon/DevOps/blob/main/Operating_System/Linux/Linux%20CLI/PNG/Screenshot%20from%202022-08-13%2005-15-22.png"> 
</p>


#  :bulb: Команда «wc»
> Команда wc отображает статистическую информацию о файле, такую как количество строк, слов, символов.
```
wc [options] [files]
```
> :mag_right: Если вы используете команду wc только с именами входных файлов, без каких-либо параметров, она будет показывать вам количество строк, слов и байтов одновременно.
```
wc avocado.txt
```


<p align="center">
<img src="https://media.giphy.com/media/o8yLq7oxbIv1HwUgJO/giphy.gif">
</p> 


В приведенном выше виде:
-   3  — количество строк
-   4  — количество слов
-   26  — количество байтов

1. Подсчитайте количество строк в файле

> :mag_right: Если вы просто хотите узнать количество строк в текстовом файле, вы можете использовать команду wc с опцией ‘l’ (line) . В основном, она подсчитывает количество строк в файле.
```
wc -l avocado.txt
```
2. Подсчитайте количество слов в файле

> :mag_right: Если вы просто хотите узнать количество слов в текстовом файле, вы можете использовать команду wc с опцией ‘w’ (word) . В ней будет отображаться количество слов с пробелами.
```
wc -w avocado.txt
```

<p align="center">
<img src="https://media.giphy.com/media/qkzFQqnHHOR3ram1ht/giphy.gif">
</p> 

3. Подсчитайте количество байтов и символов в файле

> :mag_right: Если это обычный текстовый файл, количество байтов и символов должно быть одинаковым. Но это будет отличаться для не текстовых файлов.

- Чтобы отобразить количество байтов в файле, используйте команду wc с опцией ‘c’:
```
w -c avocado.txt
```
- Чтобы отобразить количество символов в файле, используйте команду wc с опцией ‘m’:
```
w -m avocado.txt
```

<p align="center">
<img src="https://media.giphy.com/media/FmDIf699oRmhWLaexL/giphy.gif">
</p> 

4. Длина отображения самой длинной строки файла

> :mag_right: Параметр «L» команды wc отображает длину (количество символов) самой длинной строки файла.

```
wc -l avocado.txt
```
5. Отобразить количество строк, слов, символов для нескольких файлов.

> :mag_right: Вы можете использовать более одного файла с командой wc. Она будет отображать выходные данные для каждого из файлов по одному вместе с общим количеством во всех файлах.

Например, если мы хотим отобразить количество строк из двух файлов, это будет выглядеть так:
```
wc -l avocado.txt apple.txt
```

<p align="center">
<img src="https://media.giphy.com/media/qkzFQqnHHOR3ram1ht/giphy.gif">
</p>

> Вы можете дополнительно использовать wc с выводом других команд, используя pipes (|).

Например, вы можете перенаправить вывод команды ls на wc и, таким образом, что вы можете подсчитать общее количество файлов и подкаталогов в данной заданной директории.
```
ls | wc -l
```
> :mag_right: Возможно, вы заметили, что вывод команды wc состоит из имен файлов. Если вы просто хотите получить номер без имени файла, вы можете использовать его с командой cut и избавиться от имени файла из вывода.

<p align="center" width="100%">
    <img src="https://github.com/airgedon/DevOps/blob/main/Operating_System/Linux/Linux%20CLI/PNG/Screenshot%20from%202022-08-13%2005-53-04.png"> 
</p>
