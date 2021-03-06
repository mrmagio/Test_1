## Привет!

1. Создали аккаунт на github
2. Создать локальный репозиторий
3. "Подружить" ваш локальный и удалённый репозитории. Gihub при создании нового репозитория подскажет как это можно сделать
4. Отправить `push` ваш локальный репозиторий в удалённый (на Github), при этом вам, возможно, нужно будет авторизоваться на удалённом репозитории.
5. Провести изменения "с другого компьютера".
6. Выкачать `pull` актуальное состояние из удалённого репозитория.

1. Это какой-то проект на гитхаб аккаунте.


1. Делаем `fork` интересующего нас репозитория.
2. Делаем `git clone` для нашей версии этого репозитория.
3. После этого мы создаём ветку с предлагаемыми изменениями
4. Производим изменеия толко в этой ветке.
5. Отправляем эти изменения на свой аккаунт `push`.
6. В окне на гитхаб появляется возможность отправить pull request.

## Возможные проблемы.

Может встретится такая пролема: 
> После создания репозитория на Githab, при попытке связать этот репозиторий с локальным репозиторием, после ввода команды `git remote add origin https://github.com/mrmagio/имя репозитория` git выдаёт ошибку: `remote origin already exists`. Если ввести команду `git remote rm origin`, то ошибка в git больше не появляется. Можно продолжить работать с удалённым репозиторием. 

Концепция remote-это просто URL-адрес вашего удаленного репозитория.

Это origin псевдоним, указывающий на этот URL-адрес. Поэтому вместо того, чтобы писать весь URL-адрес каждый раз, когда мы хотим отправить что-то в наш репозиторий, мы просто используем этот псевдоним и запускаем:

git push -u origin master

Сообщаем git push нашему коду из нашей локальной главной ветви в удаленный исходный репозиторий.

Всякий раз, когда мы клонируем репозиторий, git по умолчанию создает для нас этот псевдоним. Кроме того, всякий раз, когда мы создаем новое хранилище, мы просто создаем его сами.

В любом случае, мы всегда можем изменить это имя на все, что нам нравится, запустив это:

git remote rename [current-name] [new-name]
Поскольку он хранится на стороне клиента приложения git (на нашей машине), его изменение ни на что не повлияет в процессе разработки, ни в нашем удаленном репозитории. Помните, что это всего лишь имя, указывающее на адрес.

Единственное, что меняется здесь при переименовании псевдонима, - это то, что мы должны объявлять это новое имя каждый раз, когда мы помещаем что-то в наш репозиторий.

git push -u my-remote-alias master

Очевидно, что одно имя не может указывать на два разных адреса. Вот почему вы получаете это сообщение об ошибке. На вашем локальном компьютере уже есть псевдоним origin. Чтобы узнать, сколько у вас псевдонимов и каковы они, вы можете запустить эту команду:

git remote -v
Это покажет вам все псевдонимы, которые у вас есть, плюс соответствующие URL-адреса.

Вы также можете удалить их, если вам нравится запускать это:

git remote rm my-remote-alias
Итак, вкратце:
узнайте, что у вас уже есть,
удалите или переименуйте их,
добавьте свои новые псевдонимы.