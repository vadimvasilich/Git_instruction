![logo](logo.png)
# Работа с Git
## 1. Проверка наличия установленного Git
В терминале выполнить команду `git version`

Если Git установлен, появится сообщение о версии программы, иначе появится сообщение об ошибке.

## 2. Установка Git

Загружаем последнюю версию Git с сайта. 

 https://git-scm.com/book/en/v2/Getting-Started-Installing-Git

 Устанавливаем с параметрами по умолчанию.

## 3. Настройка Git

 * __При первом использовании Git нужно представиться__

Вводим кйоманды:
```
git config --global user.email "ВАШ email"
git config --global user.name "ВАШЕ Имя"
```
* __Создаём файл в папке с обучением__
* __Инициализация репозитория командой `git init`__

## 4. Создание репозитория
После создания рабчей папки нужно инициализировать там репозиторий. Это можно зделать командой:
```
git init
```
Получить информацию о состоянии текущего файла нам помоможет команда:
```
git status
```
## Команды:
* __`git add name_file`__ - Запись изменений в репозиторий, добавляет файл или файлы (через запятую) к следующему коммиту;
* __`git commit -m "Комментарий"`__ -создаёт коммит;
> * __`git commit -am "Комментарий"`__ -выполняет две команды сразу add + commit;

позволяют нам добавить изменённый файл к коммиту и сохраняют коммит с комментарием об изменениях, соответственно.


## _Сохрани подсказку_
![Здесь](commands.png)

## 5. Игнорирование файлов

Чтобы исключить из отслеживания определенные файлы или папки, нужно создать там и в репозитории файл ***.gitignore*** 
и записать в нём названия игнорируемых файлов или шаблоны соответствующие этим файлам или папкам (*.jpeg или *.png).

## 6. Создание веток в Git

Текущая ветка будет отмечена зеленым цветом и звёздочкой:
**\*master**
    
Создать ветку можно командой:
```
git branch "name branch"
```
Врезультате создаётся новый указатель на текущий коммит.

Ветка в Git - это простой перемещаемый показатель на один из коммитов, обычно последний в цепочке коммитов.

По умолчанию имя основной ветки - это *master*

Список веток в репозитории можно посмотреть с помощью команды `git branch`.

Переименовать ветку:
```
git branch -m master main
```
- ветку приходится переименовывать каждый раз в ручную через команду git branch -m master main.

**Создать новую ветку с одновременным переходом в неё можно командой:**
```
git checkout -b "имя ветки"
```

## 7. Слияние веток и разрешение конфликтов

Для слияния выбранной ветки и текущей нужно выполнить команду:
```
git merge " название выбранной ветки"
```
Если текст в двух ветках не совпадает, git выделит конфликтную часть текста цветом. При этом vscode предлагает различные способы разрешения спорной ситуации:


## 8. Удаление веток

Если необходимо удалить ветку, нужно ввести команду
```
git branch -d "name branch"
```
Удаления не произойдет если ты находишься в удаляемой ветке, а так же если слияние ещё не произошло. Но в последнем случае удалить ветку можно принудительно командой:
```
git branch -D "name branch"
```
##  9. Графическая визуализация

Если мы хотим вывести дерево коммитов графически нужно ввести команду:
```
git log --graph
либо в одну строку:
git log --oneline --graph
```

## 10. Навигация между ветками и коммитами

Чтобы переместиться в другую ветку достаточно ввести  команду
__`git checkout`__  и добавить имя ветки в которую хотите переместиться. Например:
```
git checkout master
```

## 11. Журнал истории коммитов

Если нужно просмотреть историю коммитов введите команду:
```
git log
```
Её вариация  __`git log --oneline`__  - выводит в терминал сокращенный журнал коммитов.


## 12. Команда git diff

Команда 
```
 git diff
 ```
  - позволяет увидеть разницу между закомминченным файлом и текущим состоянием

## 13. Работа с удаленным репозиторием

1. Чтобы синхронизировать репозиторий на github и персональном устройстве для возможности одновременной работы нескольких пользователей;
- первоначально создадим его на github
- потом создаём локальный репозиторий с текстом и коммитом
- изменения локального репозитория нужно отправить в удаленный командой:
```
git push
```
Для этого нужно будет авторизоваться на github единожды
- обновить страницу на сайте и увидим изменения в репозитории.

2. Для того чтобы перенести чей-либо репозиторий с github выполняем следующий алгоритм:
- нужно найти интересующий репозиторий в поиске на github
- сделать fork в свой аккаунт на  github
- скопировать путь к репозиторию
- открыть необходимую директорию в vscode и дать команду 
```
git clone <путь к репозиторию на github>
```
и клонируем в подготовленную папку размещенную локально.
- перходим в папку командой  `cd "имя папки"`

Далее работаем локально, вносим и сохраняем изменения и как-только мы захотим перенести сделанные изменения в удаленный репозиторий, вводим команду
```
git push
```
 git может дать подсказку с полным указанием пути к удаленному репозиторию и тогда мы воспользуемся ею. Таким образом у нас синхронизируется локальный и удаленный репозиторий.

 3.  Pull Request

 Если мы хотим внести своё предложение в интересующий проект выполняем процедуры описанные в подпункте 3.
 Локально создаем новую ветку, создаем другой файл README.md, там прописываем свои предложения.
 Коммитим и отправляем изменения себе на удаленный репозиторий командой `git pull`.
 После обновления страницы появляется зеленая кнопка `Compare&Pull request`, добавляем сопроводительную записку и отправляем своё предложение.
