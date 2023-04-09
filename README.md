![yambd_workflow](https://github.com/Romanroman99/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg?event=push)
### Проект Yamdb - это проект, направленный на оценку любых произведений!

```
С помощью данной плотформы люди могут обмениваться отзывами о произведениях, комментировать отзывы других участников.
```

### Мы использовали данный стек технологий для проектирования проекта:
```
Django
DRF
Python
```

### Ссылка на документацию:
```
http://127.0.0.1:8000/redoc/
```

### Задачи были распределены данным образом:
```
Настасья Мартынова:
  Писала всю часть, касающуюся управления пользователями:  
    - систему регистрации и аутентификации,
    - права доступа,
    - работу с токеном,
    - систему подтверждения через e-mail.
  
Роман Романцов:
  Писал модели, view и эндпойнты для:
    - произведений,
    - категорий,
    - жанров;
    - реализовал импорт данных из csv файлов.
 
Вадим крамаренко:
  Работал над:
    - отзывами,
    - комментариями,
    - рейтингом произведений.
```

## Как запустить проект на сервере с Ubuntu

Склонируйте репозиторий и перейдите в него в командной строке:

```
git clone https://github.com/whodef/yamdb_final.git
```

Выполните вход на свой удаленный сервер

Установите docker на сервер:

```
sudo apt install docker.io
```

Установите docker-compose на сервер:

```
sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
```

Запустите docker-compose:

```
docker-compose up -d --build
```

Соберите файлы статики, и запустите миграции командами:

```
docker-compose exec web python3 manage.py makemigrations
```
```
docker-compose exec web python3 manage.py migrate
```
```
docker-compose exec web python3 manage.py collectstatic --no-input
```

Создайте суперпользователя командой:

```
docker-compose exec web python3 manage.py createsuperuser
```

Команда по загрузке файла fixtures в БД
```
docker-compose exec web python3 manage.py dumpdata > fixtures.json
```

Остановить можно командой:

```
docker-compose down -v
```

### Как запустить проект:

Клонировать репозиторий и перейти в него в командной строке:

```
git clone git@github.com:litlmayn/api_yamdb.git
```

```
cd api_final_yatube
```

Cоздать и активировать виртуальное окружение:

```
python3 -m venv env
```

```
source venv/bin/activate
```

Установить зависимости из файла requirements.txt:

```
python3 -m pip install --upgrade pip
```

```
pip install -r requirements.txt
```

Выполнить миграции:

```
python3 manage.py migrate
```

Запустить проект:

```
python3 manage.py runserver
```