man - помощь
info - тоже помощь
uptime - время с последнего включения
lscpu - данные процессора
whatis - показывает что делает команда
whereis - показывает где файл
locate - показывает где файл
ls - показать что в этой директории
ls -la -R / - показать все на компьютере
Ctrl+Z - отправить процесс на background
Ctrl+C - прекратить процесс вообще
cd - сменить директорию
pwd - вывести путь где мы сейчас
~ - сокращение нашей Home директории
.. - директория которая выше
. - директория где мы сейчас
touch  - создать файл или обновить время 
cp - скопировать файл, cp -R скопировать папку
mv - перенести файл или переименовать
rm - стереть файл
mkdir - создать дирректорию
$ mkdir -p dir1/dir-inside/dir-deeper-inside
# создали папку dir-deeper-inside в папке dir-inside, которая находится в папке dir1 

cat - Чтение файлов — cat
Удаление файлов и папок — rm, rmdir, rm -r


&& - Выполняйте сразу несколько команд

$ mkdir second-project && cd second-project && touch index.html style.css
# создаём папку second-project,
# переходим в папку second-project
# и создаём в ней два файла: index.html и style.css 


Навигация
•	pwd (от англ. print working directory, «показать рабочую папку») — покажи, в какой я папке;
•	ls (от англ. list directory contents, «отобразить содержимое директории») — покажи файлы и папки в текущей папке;
•	ls -a — покажи также скрытые файлы и папки, названия которых начинаются с символа .;
•	cd first-project (от англ. change directory, «сменить директорию») — перейди в папку first-project;
•	cd first-project/html — перейди в папку html, которая находится в папке first-project;
•	cd .. — перейди на уровень выше, в родительскую папку;
•	cd ~ — перейди в домашнюю директорию (/Users/Username);
•	cd / — перейди в корневую директорию.
Работа с файлами и папками
Создание
•	touch index.html (англ. touch, «коснуться») — создай файл index.html в текущей папке;
•	touch index.html style.css script.js — если нужно создать сразу несколько файлов, можно напечатать их имена в одну строку через пробел;
•	mkdir second-project (от англ. make directory, «создать директорию») — создай папку с именем second-project в текущей папке.
Копирование и перемещение
•	cp file.txt ~/my-dir (от англ. copy, «копировать») — скопируй файл в другое место;
•	mv file.txt ~/my-dir (от англ. move, «переместить») — перемести файл или папку в другое место.
Чтение
•	cat file.txt (от англ. concatenate and print, «объединить и распечатать») — распечатай содержимое текстового файла file.txt.
Удаление
•	rm about.html (от англ. remove, «удалить») — удали файл about.html;
•	rmdir images (от англ. remove directory, «удалить директорию») — удали папку images;
•	rm -r second-project (от англ. remove, «удалить» + recursive, «рекурсивный») — удали папку second-project и всё, что она содержит.
Полезные возможности
•	Команды необязательно печатать и выполнять по очереди. Можно указать их списком — разделить двумя амперсандами (&&).
•	У консоли есть собственная память — буфер с несколькими последними командами. По ним можно перемещаться с помощью клавиш со стрелками вверх (↑) и вниз (↓).
•	Чтобы не вводить название файла или папки полностью, можно набрать первые символы имени и дважды нажать Tab. Если файл или папка есть в текущей директории, командная строка допишет путь сама.
Например, вы находитесь в папке dev. Начните вводить cd first и дважды нажмите Tab. Если папка first-project есть внутри dev, командная строка автоматически подставит её имя. Останется только нажать Enter.








git version – версия ГИТ
git config
$ git config --list
$ git config --global user.name "ваше имя или ник латиницей" 
$ git config --global user.email ваша электронная почта
$ cat ~/.gitconfig
$ git config –list
$ git config --global user.name "User Namovich" 
# имя или ник нужно написать латиницей и в кавычках

$ git config --global user.email username@yandex.ru
# здесь нужно указать свой настоящий email

Инициализировать репозиторий можно с помощью команды git init.
•	Проверить статус, или состояние, репозитория поможет команда git status.
•	Если вы ошиблись и случайно инициализировали не ту папку, можно «разгитить» её — удалить скрытую подпапку .git.

«Разгитить» папку, если что-то пошло не так, — rm -rf .git
Разберём подробнее, что такое -rf:
ключ -r (от англ. recursive — «рекурсивно») позволяет удалять папки вместе с их содержимым;
ключ -f (от англ. force — «заставить») избавит вас от вопросов вроде «Вы точно хотите удалить этот файл? А этот? И этот тоже?»
Проверить состояние репозитория — git status
•	git add позволяет подготовить файл к сохранению.
•	git add --all подготовит к сохранению сразу все файлы.
•	git add . можно добавить в репозиторий текущую папку со всеми файлами.

Сначала команда git add сообщает Git, какие именно файлы нужно сохранить и какую их версию. Затем с помощью команды git commit происходит само сохранение

$ git commit -m 'Мой первый коммит!'
Просмотреть историю коммитов — git log

1.	Для генерации SSH-пары можно использовать программу ssh-keygen. Откройте терминал и введите следующую команду.
Скопировать кодBASH
$ ssh-keygen -t ed25519 -C "электронная почта, к которой привязан ваш аккаунт на GitHub"

# скопировать содержимое ключа в буфер обмена:
$ clip < ~/.ssh/id_rsa.pub
# для ed25519:
$ clip < ~/.ssh/id_ed25519.pub
Привязать удалённый репозиторий к локальному — git remote add

$ cd ~/dev/first-project
$ git remote add origin git@github.com:%ИМЯ_АККАУНТА%/first-project.git

Убедиться, что репозитории связаны, — git remote -v

Отправить изменения на удалённый репозиторий — git push

$ git push -u origin main # Если команда приведёт к ошибке, попробуйте 
                          # заменить main на master.

Подробнее о том, зачем нужен README.md
Как правило, в README.md проекта можно найти следующую информацию:
1.	Название проекта и его краткое описание: кем создан, для чего, какие решает задачи и какие закрывает проблемы.
2.	Технологии, которые применяются в проекте. В чём его отличие от аналогичных.
3.	Документация проекта — подробная инструкция о том, что представляет собой проект.
4.	Планы проекта, если они есть.



