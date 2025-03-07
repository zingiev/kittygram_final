#  Как работать с репозиторием финального задания
[![Main Kittygram workflow](https://github.com/zingiev/kittygram_final/actions/workflows/main.yml/badge.svg)](https://github.com/zingiev/kittygram_final/actions/workflows/main.yml)

## Что нужно сделать

Настроить запуск проекта Kittygram в контейнерах и CI/CD с помощью GitHub Actions

## Как проверить работу с помощью автотестов

В корне репозитория создайте файл tests.yml со следующим содержимым:
```yaml
repo_owner: ваш_логин_на_гитхабе
kittygram_domain: полная ссылка (https://доменное_имя) на ваш проект Kittygram
taski_domain: полная ссылка (https://доменное_имя) на ваш проект Taski
dockerhub_username: ваш_логин_на_докерхабе
```

Скопируйте содержимое файла `.github/workflows/main.yml` в файл `kittygram_workflow.yml` в корневой директории проекта.

Для локального запуска тестов создайте виртуальное окружение, установите в него зависимости из backend/requirements.txt и запустите в корневой директории проекта `pytest`.

## Чек-лист для проверки перед отправкой задания

- Проект Taski доступен по доменному имени, указанному в `tests.yml`.
- Проект Kittygram доступен по доменному имени, указанному в `tests.yml`.
- Пуш в ветку main запускает тестирование и деплой Kittygram, а после успешного деплоя вам приходит сообщение в телеграм.
- В корне проекта есть файл `kittygram_workflow.yml`.


# Kittygram
## Описание проекта
Kittygram - это социальная сеть для публикации фотографий ваших любимых котов. Пользователи могут:

- Добавлять фотографии своих котов
- Указывать дату рождения питомца
- Выбирать окрас кота
- Добавлять достижения и награды

## Используемые технологии
- Python/Django (бэкенд)
- React (фронтенд)
- PostgreSQL (база данных)
- Docker (контейнеризация)

## Установка и запуск
### Требования
- Docker
- Docker Compose

## Настройка
1. Заполните необходимые параметры .env файла:
```bash
POSTGRES_DB=kittygram
POSTGRES_USER=postgres
POSTGRES_PASSWORD=your-password
DB_HOST=db
DB_PORT=5432
DEBUG=True
SECRET_KEY=your-secret-key
```
2. Запустите контейнеры:
```bash
docker-compose up -d 
```
3. Выполните миграции и соберите статические файлы:
```bash
docker-compose exec web python manage.py migrate
docker-compose exec web python manage.py collectstatic
```
4. Создайте суперпользователя:
```bash
docker-compose exec web python manage.py createsuperuser
```
## Доступ к приложению
http://localhost:9000

## Автор
Ясин Зингиев

## Благодарности
Особая благодарность всем любителям котов, вдохновляющим на создание этого проекта! 🐱
