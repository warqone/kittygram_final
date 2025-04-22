# Kittygram
## _Как инстаграм, но только для кошек._
___
[![Main Kittygram workflow](https://github.com/warqone/kittygram_final/actions/workflows/main.yml/badge.svg)](https://github.com/warqone/kittygram_final/actions/workflows/main.yml)

## Возможности проекта

- Выкладывать фотографии своих шерстяных друзей.
- Добавлять своим котикам достижения.
- Редактировать данные о своих котиках.
- Просматривать фотографии и информацию о котиках других пользователей.
- Так же доступно API для интеграции.
___
## Стек использованных технологий

Dillinger uses a number of open source projects to work properly:

- [Django](https://www.djangoproject.com/download/) - свободный фреймворк для разработки быстрых и безопасных веб-приложений и сайтов на языке Python.
- [Django Rest Framework](https://www.django-rest-framework.org/) - набор инструментов для создания веб-сервисов и API на основе фреймворка Django.
- [PostgreSQL](https://www.postgresql.org/) - бесплатная объектно-реляционная система управления базами данных (СУБД) с открытым исходным кодом.
- [Node.JS](https://nodejs.org/en) - платформа с открытым исходным кодом для работы с языком JavaScript, построенная на движке Chrome V8.
- [Docker](https://www.docker.com/) - платформа с открытым исходным кодом для автоматизации разработки, доставки и развёртывания приложений. 
- [Yandex Cloud](https://yndx.auth.yandex.cloud/install?uuid=a0c6a64e-1be8-4553-bf53-7660e8e356f5&retpath=https%3A%2F%2Fyandex.cloud%2Fru%3Futm_referrer%3Dhttps%253A%252F%252Fyandex.ru%252F) - облачная платформа от компании «Яндекс», которая предоставляет широкий спектр услуг для хранения данных, вычислений и разработки приложений.
___
## Как развернуть проект (локально)
Склонируйте репозиторий и перейдите в него
```sh
git clone git@github.com:warqone/kittygram_final.git
cd kittygram_final
```
Создайте файл настроек (.env) и заполните его по образцу ниже.
```sh
POSTGRES_DB=kittygram
POSTGRES_USER=kittygram_user
POSTGRES_PASSWORD=kittygram_password
DB_HOST=db
DB_PORT=5432
ALLOWED_HOSTS=<your_domain> localhost 127.0.0.1
MEDIA_ROOT=/app/media
DEBUG=False #  (optinal)
SQLITE=False #  (optional)
```
Откройте терминал bash или docker, перейдите в директорию kittygram_final
```sh
docker compose -f docker-compose.production.yml up -d --build
```
После сборки образов соберите статистические файлы и выполните миграции
```sh
docker compose -f docker-compose.production.yml exec backend python manage.py migrate
docker compose -f docker-compose.production.yml exec backend python manage.py collectstatic --noinput
docker compose -f docker-compose.production.yml exec backend cp -r /app/backend_static/. /backend_static/static/
```

### Ваш проект готов к работе! (перейдите по [адресу](https://127.0.0.1:9000))
___
## Автор - [warqone](https://github.com/warqone)
