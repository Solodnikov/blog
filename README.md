# blog

![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![Django](https://img.shields.io/badge/django-%23092E20.svg?style=for-the-badge&logo=django&logoColor=white)
![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white)
![Postgres](https://img.shields.io/badge/postgres-%23316192.svg?style=for-the-badge&logo=postgresql&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)
<!-- добавить картинку -->

### Описание проекта

Социальная сеть, которая позволяет пользователям делится записями, размещать фотографии, подписываться на других пользователей и комментировать их записи. Также пользователи могут создавать сообщества по интересам.

### Проект работает и доступен по адресу

`http://45.90.218.173/`

### Развертывание проекта

* клонируйте проект

   `https://github.com/Solodnikov/blog`

* порядок запуска в докер контейнерах

    `docker-compose up -d --build` - сбрка и запуск контейнеров

    `docker-compose exec web python manage.py makemigrations` - создание миграций

    `docker-compose exec web python manage.py migrate` - выполнение миграций

    `docker-compose exec web python manage.py createsuperuser` - создание суперюзера

    `docker-compose exec web python manage.py collectstatic --no-input` - сбор статистики

* создайте файл `.env` в корневой директории проекта:
    
    ```
    # .env example
    DB_ENGINE=django.db.backends.postgresql
    DB_NAME=postgres
    POSTGRES_USER=postgres
    POSTGRES_PASSWORD=postgres
    DB_HOST=db
    DB_PORT=5432
    ```

* проект настроен для работы на локальном сервере по адресу

    `http://127.0.0.1:80`

* для запуска проекта на выделенном сервере необходимо изменить настройки файла `nginx/default.conf`: в настройках `server_name 127.0.0.1;` указать IP выделенного сервера, где будет развернут проект.
