![Kittygram CI/CD](https://github.com/harrows/kittygram_final/actions/workflows/main.yml/badge.svg)

# Kittygram — сервис для публикации котиков

Kittygram — это учебный проект, позволяющий пользователям публиковать фотографии своих котиков, отмечать их достижения и просматривать питомцев других пользователей.

## Стек технологий

- Python 3.11  
- Django / Django REST Framework  
- Postgres  
- Docker / Docker Compose  
- Nginx  
- GitHub Actions (CI/CD)

## Развертывание проекта в Docker

### 1. Клонировать репозиторий

```bash
git clone https://github.com/harrows/kittygram_final.git
cd kittygram_final
```
### 2. Создайте файл backend/.env и заполните его:

```bash
SECRET_KEY=your_secret_key
DEBUG=False
ALLOWED_HOSTS=kittygram-prakt.duckdns.org,127.0.0.1,localhost

DB_ENGINE=django.db.backends.postgresql
DB_NAME=kittygram
DB_USER=kittygram_user
DB_PASSWORD=your_db_password
DB_HOST=db
DB_PORT=5432
```
### 3. Запустить проект
```bash
docker compose -f docker-compose.production.yml up -d
```
Контейнеры будут автоматически собраны и запущены:


backend (Django)

frontend (React)

gateway (Nginx)

db (Postgres)


### 4. Применить миграции и собрать статику
```bash
docker compose -f docker-compose.production.yml exec backend python manage.py migrate
docker compose -f docker-compose.production.yml exec backend python manage.py collectstatic --noinput
```
После этого проект полностью готов к работе.

## Автор
Dmitrii (harrows)