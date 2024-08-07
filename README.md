# Приложение для построения маршрута движения автопоезда

Это приложение разработано для построения маршрутов движения автопоездов с использованием различных API и поиска ближайших АЗС вдоль маршрута.

Приложение использует следующие API:

Open Elevation API
WeatherAPI
TomTom API

## Установка

1. **Настройка окружения**

Структура файла .env

SECRET_KEY= django secret key
DEBUG= true/false

Настройки базы данных:
POSTGRES_DB=
POSTGRES_USER=
POSTGRES_PASSWORD=
POSTGRES_HOST=
POSTGRES_PORT=

Oauth Google Авторизация:
SOCIAL_AUTH_GOOGLE_OAUTH2_KEY=
SOCIAL_AUTH_GOOGLE_OAUTH2_SECRET=

Настройки суперпользователя:
EMAIL_HOST_USER=
EMAIL_HOST_PASSWORD=

API ключи:
WEATHERAPI_API=
TOMTOM_API=

Для работы приложения создайте файл .env в корне приложения и заполните
его используя подсказки файла .env.sample


2. **Установка зависимостей**



```bash
Установите зависимости из файла pyproject.toml
>>>poetry install

Примените миграции

>>>python manage.py migrate

Создайте суперпользователя командой

>>>python manage.py csu

Получите данные о координатах АЗС с сайта https://rss.tatneft.ru/outer/azs/get_xml_list?region_id=0&fuel_type_id=0 (сохранится в "gas_stations.xls") командой

>>>python manage.py upload_table

Заполните базу данных данными из таблицы (можно использовать повторно)
командой

>>>python manage.py fill_database

Запустите сервер

>>>python manage.py runserver


Доступ к приложению

После запуска сервера приложение будет доступно по адресу http://localhost:8000/.
