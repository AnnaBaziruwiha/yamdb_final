# YAMDB

![Django-app workflow](https://github.com/AnnaBaziruwiha/yamdb_final/actions/workflows/yamdb_workflow.yaml/badge.svg)

### Описание
Проект YaMDb собирает отзывы (Review) пользователей на произведения (Titles). Произведению может быть присвоен жанр (Genre).
Произведения делятся на категории: Книги, Фильмы, Музыка. Список категорий может быть расширен администратором.

Развернутый проект можно посмотреть [здесь](http://abzrwh.co.vu/api/v1/titles/)

### Технологии
Python 3.9.0
Django 3.0.5
gunicorn 20.0.4

### Ресурсы
**auth**: аутентификация

**users**: пользователи

**titles**: произведения, к которым пишут отзывы

**categories**: категории произведений

**genres**: жанры произведений

**reviews**: отзывы на произведения

**comments**: комментарии к отзыву

### Запуск проекта в dev-режиме
- Создайте в корне проекта файл .env и пропишите в нем следующие переменные окружения:
```sh
DB_ENGINE # укажите, какая подсистема хранения будет использоваться
DB_NAME # имя базы данных
POSTGRES_USER # логин для подключения к базе данных
POSTGRES_PASSWORD # пароль для подключения к базе данных
DB_HOST # название сервиса
DB_PORT # порт для подключения к базе данных
```
- Находясь в директории проекта, запустите docker-compose:
```sh
docker-compose up -d
```
- Соберите статику проекта в папку static
```sh
docker-compose exec web python manage.py collectstatic
```
- Выполните миграции в два этапа:
```sh
docker-compose exec web python manage.py migrate auth
docker-compose exec web python manage.py migrate --run-syncdb
```
- Создайте суперпользователя
```sh
docker-compose exec web python manage.py createsuperuser
```
- Заполните базу начальными данными
```sh
docker-compose exec web python manage.py loaddata fixtures.json
```

### Контакты
Еще больше моих проектов ищите [тут](https://github.com/AnnaBaziruwiha)

Предложения и пожелания пишите [сюда](abaziruwiha@gmail.com)

Мой [linkedin](https://www.linkedin.com/in/annabaziruwiha/)
